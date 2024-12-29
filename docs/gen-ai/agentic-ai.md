

Phi Data - It is an open source platform to build, ship and monitor agentic systems. 
Able to build AI agents, 
able to build multimodel agents , 
able to create agentic workflows more complex agentic workflows.
This is super helpful if you just have some amount of domain knowledge, you should be able to build it in an amazing way. 
The best part about this is that , we can choose any LLM and turn any LLM into an agent 
you'll be able to add knowldge provide domain specific information to solve your problems 
there is documentation where we can refer and can work with how many different kind of agents you can specifically work with 
you can also go ahead and write your own prompts / tools / knowledge / memory 
you will also able to integrate with different models like OpenAI /Anthropic / AWS bedrock / Azure / gemini vertex / hugging face / grok / nvidia / ollama

Financial Agent - Create an application and internally it will have multiple agents
Usage
    probably we can ask question like can u summarize and recommend about the stock of nvidia through chatbot
    Now chatbot contact agents 
        the first agent will be AI agent (autonomous) which will be doing all the interaction to get the details of the stock
        the second AI agent that it will try to probably get some information(specifically what new information have) from the news / from the web search, combine all those information and then should interact with LLM model and come to conclusion 
        saying that what all recommendation specifically have for that stock


project
    Open vs code 
    create python enviromnet - "conda create -p venv python==3.12"
    Activate the enviromnet - "conda activate venv/"
    add file requirements.txt (phidata / python-dotenv / yfinace / packaging / duckduckgo-search / fastapi / uvicorn / groq / openai)
        duckduckgo - tool specifically used by agent to do any kind of web search 
        fastapi - internally when u want to run this in the cloud , phidata will be requiring fastapi as front end application 
        groq - fast ai inferencing , provides open source libraries and can use for some number of requests  which is completely free
    install requirements - "pip install -r requirements.txt"
    get groq api key from dev console of groq platform (https://console.groq.com/keys) and usually starts with "gsk"
    similarlu get api keyu from phidata app (https://www.phidata.app/) and usually starts with "phi"
    Add .env file
        PHI_API_KEY="phi-kgZDYxoZlnxfIP5OUt2-YFRocaLMMqiwbbUF3d4Kh0Y"
        GROQ_API_KEY="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"
        OPENAI_API_KEY=""
    or pass / set in the terminal like
        setx GROQ_API_KEY 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

    create file - financial_agent.py
        from phi.agent import Agent
        from phi.model.groq import Groq
        from phi.tools.yfinance import YFinanceTools
        from phi.tools.duckduckgo import DuckDuckGo
        from dotenv import load_dotenv

        import os
        import openai

        openai.api_key=os.getenv("OPENAI_API_KEY")
        load_dotenv()

        ## Web search agent
        web_search_agent=Agent(
            name="Web Search Agent",
            role="Search the web for the information",
            model=Groq(id="llama3-groq-70b-8192-tool-use-preview"),
            tools=[DuckDuckGo()],
            instructions=["Always include sources"],
            show_tools_calls=True,
            markdown=True,
        )

        ## Financial agent
        finance_agent=Agent(
            name="Finance AI Agent",
            model=Groq(id="llama3-groq-70b-8192-tool-use-preview"),
            tools=[
                YFinanceTools(stock_price=True, analyst_recommendations=True, stock_fundamentals=True, company_news=True),
            ],
            instructions=["Use tables to display the data"],
            show_tools_calls=True,
            markdown=True,
        )

        multi_ai_agent=Agent(
            team=[web_search_agent, finance_agent]
            instructions=["Always include sources", "Use tables to display the data"],
            show_tools_calls=True,
            markdown=True,
        )

        multi_ai_agent.print_response("Summarize analyst recommendation and share the latest news for NVDA", stream=True)

    create file - playground.py
        import openai
        from phi.agent import Agent
        import phi.api
        from phi.model.openai import OpenAIChat
        from phi.model.groq import Groq
        from phi.tools.yfinance import YFinanceTools
        from phi.tools.duckduckgo import DuckDuckGo
        from dotenv import load_dotenv
        from phi.playground import Playground, serve_playground_app

        import os
        import phi
        
        load_dotenv()
        phi.api=os.getenv("PHI_API_KEY")

        ## Web search agent
        web_search_agent=Agent(
            name="Web Search Agent",
            role="Search the web for the information",
            model=Groq(id="llama3-groq-70b-8192-tool-use-preview"),
            tools=[DuckDuckGo()],
            instructions=["Always include sources"],
            show_tools_calls=True,
            markdown=True,
        )

        ## Financial agent
        finance_agent=Agent(
            name="Finance AI Agent",
            model=Groq(id="llama3-groq-70b-8192-tool-use-preview"),
            tools=[
                YFinanceTools(stock_price=True, analyst_recommendations=True, stock_fundamentals=True, company_news=True),
            ],
            instructions=["Use tables to display the data"],
            show_tools_calls=True,
            markdown=True,
        )
        
        app=Playground(agents=[finance_agent, web_search_agent]).get_app()

        if __name__=="__main__":
            serve_plaground_app("playground:app", reload=True)

