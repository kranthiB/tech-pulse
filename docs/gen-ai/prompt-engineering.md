---
id: gen-ai/prompt-engineering
title: Prompt Engineering
sidebar_label: Prompt Engineering
next_page: gen-ai/llm-tier
---

Table of contents
=================

<!--ts-->
   * [Prompt Engineering](#prompt-engineering-unlocking-the-power-of-generative-ai)
      * [What is Prompting?](#what-is-prompting)
      * [Designing a Prompt: A 5-Step Framework](#designing-a-prompt-a-5-step-framework)
        * [1. Task](#1-task)
        * [2. Context](#2-context)
        * [3. References](#3-references)
        * [4. Evaluate](#4-evaluate)
        * [5. Iterate](#5-iterate)
            * [Mnemonic to Remember Iteration Methods](#mnemonic-to-remember-iteration-methods)
        * [Mnemonic to Remember the Framework](#mnemonic-to-remember-the-framework)
      * [Multimodal Prompting](#multimodal-prompting)
        * [Examples of Multimodal Usage](#examples-of-multimodal-usage)
      * [Major Issues When Using AI Tools](#major-issues-when-using-ai-tools)
        * [1. Hallucinations](#1-hallucinations)
        * [2. Biases](#2-biases)
        * [Mitigating Issues](#mitigating-issues)
      * [Using AI Responsibly](#using-ai-responsibly)
      * [Design Prompts for Everyday Work Tasks](#design-prompts-for-everyday-work-tasks)
        * [Prompt Library](#prompt-library)
          * [Example 1: Writing an Email](#example-1-writing-an-email)
          * [Example 2: Planning a Game Launch](#example-2-planning-a-game-launch)
          * [Example 3: Scheduling Staff Shifts](#example-3-scheduling-staff-shifts)
      * [Speed Up Data Analysis](#speed-up-data-analysis)
        * [Example Dataset](#example-dataset)
        * [Prompts for Data Analysis](#prompts-for-data-analysis)
        * [Understanding Complex Formulas](#understanding-complex-formulas)
      * [Building Presentations](#building-presentations)
        * [How Generative AI Can Help](#how-generative-ai-can-help)
        * [Example Prompts](#example-prompts)
          * [Structuring a Presentation](#structuring-a-presentation)
          * [Creating Visuals for the Presentation](#creating-visuals-for-the-presentation)
      * [Use AI as a Creative or Expert Partner](#use-ai-as-a-creative-or-expert-partner)
        * [Advanced Prompting Techniques](#advanced-prompting-techniques)
          * [Prompt Chaining](#prompt-chaining)
          * [Chain of Thought Prompting](#chain-of-thought-prompting)
          * [Tree of Thought Prompting](#tree-of-thought-prompting)
          * [Pro Tips for Prompting](#pro-tips-for-prompting)
        * [AI Agents](#ai-agents)
          * [Types of AI Agents](#types-of-ai-agents)
          * [Designing Effective AI Agents](#designing-effective-ai-agents)
<!--te-->

## Prompt Engineering: Unlocking the Power of Generative AI

### What is Prompting?

Prompting is the process of providing specific instructions to a generative AI tool to receive new information or to achieve a desired outcome on a task. This interaction can encompass various modalities, including:

- **Text**
- **Images**
- **Videos**
- **Audio**
- **Code**

The quality and structure of the prompt often directly influence the relevance and usefulness of the AI-generated output.

-----

### Designing a Prompt: A 5-Step Framework

Creating an effective prompt is essential for achieving high-quality results from generative AI tools. Here is a 5-step framework to guide you:

#### 1. Task
Define what you want the AI to do. For example:
- If your friend's birthday is approaching and they're really into anime, you could start with:  
  *"Suggest a gift related to anime for my friend's birthday."*

While this prompt might yield decent results, you can make it more unique and specific by incorporating two additional elements:

- **Persona:** Define the role you want the AI to embody. For example:  
  *"Act as an anime expert to suggest an anime gift for my friend's birthday."*  
  This adjustment leads to more specific results, potentially categorized by different genres.

- **Output Format:** Specify the desired format of the response. For instance:  
  *"Organize that data into a table."*

#### 2. Context
Provide as much relevant information as possible. More context typically leads to better outputs. For example:  
*"Act as an anime expert to suggest an anime gift for my friend's birthday. She is turning 29 years old, and her favorite animes are Shangri-la Frontier, Solo Leveling, and Naruto Treasures."*  
This additional context helps the AI tailor its suggestions more precisely.

#### 3. References
Include examples to clarify your expectations. If explaining your requirements in words proves challenging, examples can help. For instance, share past birthday presents that the person enjoyed to guide the AI in crafting suitable suggestions.

#### 4. Evaluate
After receiving the AI's output, ask yourself: *"Is this result aligned with what I wanted?"* If it isn’t, proceed to the next step.

#### 5. Iterate
Prompting is rarely a one-and-done process. It's an iterative cycle where you refine the prompt to achieve the desired results. Here are four effective methods for iteration:

1. **Revisit the Prompting Framework:** Consider adding more references, providing additional examples, offering more context, or introducing a persona if you haven’t already.

2. **Separate Prompts into Shorter Sentences:** Simplify complex instructions into smaller, manageable parts. For example:
   - Instead of:  
     *"Summarize the key data points and information in the report. Then create visual graphs from the data and shorten the key information into bullets."*
   - Try:  
     *"1. Summarize the key data points and information in the report.*  
     *2. Create visual graphs with the data you summarized.*  
     *3. Shorten the key information you summarized into bullets."*

3. **Try Different Phrasing or Analogous Tasks:** If the output feels dull or uninspired, reframe the task. For example, instead of asking for a marketing plan, try:  
   *"Write a story about how this product fits into the lives of our target customer demographics."*  
   This can lead to more engaging and creative results.

4. **Introduce Constraints:** Narrow the focus by specifying constraints. For example:
   - Instead of:  
     *"Generate a playlist for a road trip."*
   - Add constraints like:  
     *"Only use Brazilian music."*  
     *"Only include chilled and adventurous tempos."*  
     *"Only songs about heartbreak."*

##### Mnemonic to Remember Iteration Methods
Use the phrase *"Refine Sentences And Constraints Thoughtfully"* to recall these methods:
- **Revisit the Prompting Framework**
- **Separate Prompts into Shorter Sentences**
- **Analogous Tasks and Different Phrasing**
- **Introduce Constraints**

#### Mnemonic to Remember the Framework
Use the phrase *"Thoughtfully Create Really Excellent Inputs"* to recall the 5-step framework:
- **Task**
- **Context**
- **References**
- **Evaluate**
- **Iterate**

-----

### Multimodal Prompting

Multimodal prompting expands the interaction beyond text, allowing generative AI tools to process and generate outputs in various modalities such as images, audio, video, and code. Many advanced AI models, like Gemini, support these capabilities. This doesn’t fundamentally change the principles of effective prompting but requires careful specification of inputs, outputs, and context.

For example, if you designed a new nail art collection and want to market it on social media, you could input:

*"Write a social media post featuring this image. The post should be fun, short, and focus on the fact that it's a collection of new designs I'm selling."*  

![SMP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0001-SMP.png)

#### Examples of Multimodal Usage
- **Suggest recipes based on a photo of the ingredients in your fridge.**
- **Design a visually appealing digital teaser to promote an upcoming event:**  
  *"Incorporate the brand's logo and signature colors. The teaser should be modern and engaging, featuring the event's key details such as the name, date, location, and a catchy tagline. Use dynamic elements, bold typography, and seamless transitions aligned with the brand's aesthetic. Aim for a captivating teaser that sparks curiosity and encourages audience participation."*

-----

### Major Issues When Using AI Tools

Regardless of the modality, there are two significant challenges associated with using AI tools:

#### 1. Hallucinations
Hallucinations occur when the tool provides outputs that are inconsistent, incorrect, or nonsensical. For example:
- Asking AI: *"How many R's are in the word strawberry?"*  
  The AI might respond incorrectly with: *"There are 2 R's in strawberry."*

#### 2. Biases
AI systems, trained on human-generated content, often inherit biases present in that content. These biases can include those related to gender, race, and more.

#### Mitigating Issues
To address these problems, a **human-in-the-loop** approach is recommended. Always review and verify the AI-generated outputs to ensure accuracy and fairness.

-----

### Using AI Responsibly

When leveraging AI tools, it is your responsibility to ensure that the outputs are accurate, ethical, and appropriate. Here’s a checklist for responsible AI use:

1. **Evaluate Suitability:** Ensure AI fits the task and doesn't reinforce harmful biases.
2. **Get Approval:** Obtain company consent before using AI on projects.
3. **Protect Privacy:** Use secure tools and avoid exposing sensitive data.
4. **Validate Outputs:** Review all AI-generated content before sharing.
5. **Be Transparent:** Disclose AI use to teams and clients.

By adhering to this checklist, you can ensure that AI is employed responsibly, fostering trust and promoting ethical practices.

-----

### Design Prompts for Everyday Work Tasks

This section provides examples of use cases based on the 5-step framework and iteration methods to show how generative AI tools can assist with daily work tasks.

#### Prompt Library

One common use case for generative AI is content production. For instance, writing emails:

##### Example 1: Writing an Email

*"I'm a gym manager and we have a new gym schedule. Write an email informing our staff of the new schedule. Highlight the fact that the M/W/F Cardio Blast class changed from 7:00 AM to 6:00 AM. Make the email professional and friendly, and short so that readers can skim it quickly."*  
*(See the image)*

For simple emails, tone may not be critical. However, for more important content such as essays, articles, or newsletters, tone and word choice matter greatly. Instead of vague instructions like *"write a casual summary,"* use specific phrases such as:

*"Write a summary in a friendly, easy-to-understand tone like explaining to a curious friend."*

Providing references—like past emails or articles—and asking the AI to match their tone can also improve results.

##### Example 2: Planning a Game Launch

*"I'm a marketer for a well-known video game producer known for creating immersive story-based online video games. I'm planning the launch of a new medieval fantasy roleplaying game that follows the path of a young protagonist searching for their missing partner. The game's primary audience is young adults. The game is reaching the end stages of development, and I need help creating a timeline before it goes live. Provide a rough timeline for the year leading up to its launch. Also, provide some pre-launch ideas to help generate buzz around the game."*  
*(See image)*

##### Example 3: Scheduling Staff Shifts

*"I have 10 employees. Their employee numbers are 1 through 10. Create a table that tracks weekly staffing. Create columns for day, name, and shift (morning or afternoon).  

- Employees should not be scheduled for a morning shift on the following day after they were scheduled for an afternoon shift.  
- Employees should not be scheduled for both the morning and afternoon shifts on the same day.  
- Every employee should have roughly the same number of total shifts per week."*  
*(See image)*

-----

### Speed Up Data Analysis

Generative AI can significantly streamline data analysis tasks, from creating new columns to understanding complex formulas. Here’s an example of how you can leverage AI to enhance your data workflows:

#### Example Dataset

Download the dataset from the following URL:  
[StoreData.xlsx](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/files/StoreData.xlsx)  

This dataset contains information about a grocery store chain, including store details, areas, items available, daily customer counts, and store sales.

#### Prompts for Data Analysis

1. **Calculate Average Sales Per Customer:**  
   Prompt:  
   *"Attached is an Excel sheet of store data. How can I create a new column in Sheets that calculates the average sales per customer for each store?"*

   This helps generate the formula or logic needed to compute average sales per customer.

2. **Analyze Relationships in the Data:**  
   Prompt:  
   *"Give me insights into the relationship between 'Daily Customer Count,' 'Items Available,' and 'Sales' based on the given data."*

   This can reveal patterns, trends, or correlations between variables.

#### Understanding Complex Formulas

AI tools can also demystify intricate formulas. For example:

Prompt:  
"I work at a large restaurant and I need to order inventory while my coworker is on leave. They left me with a formula to calculate how much food to order, but I don’t understand it:  

=IFERROR(ROUNDUP(MAXO, VLOOKUP(B2, Inventory!A:B,2,FALSE)*0.2 - C2) + SUMIFS(Reservations!D:D, Reservations!A:A, “>=“&TODAY(), Reservations!A:A, “<“&(TODAY()+7), Reservations!C:C,B2)* 0.12), “Check Inventory”).  

Explain what the formula means in simpler, step-by-step terms."

By breaking it down, AI can clarify each component, helping you understand its purpose and application.

Generative AI can transform mundane data analysis into a faster and more efficient process, allowing you to focus on deriving insights and making decisions

-----

### Building Presentations

Generative AI can be a powerful tool for designing and structuring professional presentations. From organizing content to generating visual elements, it simplifies the process and allows you to focus on delivering your message effectively.

#### How Generative AI Can Help

1. **Organizing Content:** Use AI to outline your presentation structure, ensuring logical flow and completeness.  
2. **Creating Visuals:** Generate custom images, graphics, or charts to enhance the visual appeal of your slides.  
3. **Writing Slide Content:** Craft concise and impactful slide text tailored to your audience.  
4. **Design Suggestions:** Get recommendations for layouts, color schemes, and fonts to match your presentation’s theme.  

#### Example Prompts

##### Structuring a Presentation

*"I’m a product designer at a headphones brand. I’m putting together a presentation for my team about what new features should be included in our next product line. The presentation includes findings from our market research on features that our 18-to-34-year-old customers want their headphones to have. These features include new colors, the ability to control playback with head movements, and noise-canceling capabilities.  

Consider the relationship between our demographics' disposable income and their most important considerations when buying headphones. How should I structure my presentation? List each slide’s topic with its key points and visuals."*

##### Creating Visuals for the Presentation

*"Generate close-up images of a pair of sleek, silver headphones on a desk in a college dorm room. They should have musical notes floating around the headphones to show that they’re playing music."*


Generative AI transforms the process of building presentations by offering creative support, reducing the effort required, and enhancing the overall quality of your slides. It enables you to deliver compelling, visually engaging presentations with ease.

-----

### Use AI as a Creative or Expert Partner

Generative AI can be leveraged not only as a tool but as a creative or expert partner to enhance problem-solving, content creation, and skill-building. By using advanced prompting techniques and AI agents, you can unlock innovative ways to collaborate with AI.

#### Advanced Prompting Techniques

##### **Prompt Chaining**

Prompt chaining guides the AI tool through a series of interconnected prompts, adding layers of complexity along the way.  

![Prompt Chaining Diagram](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0005-PCT.png)  

**Example Scenario:**  
You’re an author who has written a novel and now needs a marketing plan.  

1. **Generate Summaries:**  
   *Prompt:*  
   *“Generate three options for a one-sentence summary of this novel manuscript. The summary should be similar in voice and tone to the manuscript but more catchy and engaging.”*  

   ![Output Example](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0005-A-PCT.png)  

2. **Create a Tagline:**  
   *Prompt:*  
   *“Create a tagline that is a combination of the previous three options, with a special focus on the exciting plot twist and mystery of the book. Find the catchiest and most impactful combination. The tagline should be concise and leave the reader hooked and wanting to read more.”*  

   ![Output Example](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0005-B-PCT.png)  

3. **Design a Marketing Plan:**  
   *Prompt:*  
   *“Generate a six-week promotional plan for a book tour, including what locations I should visit and what channels I should utilize to promote each stop on the tour.”*  

   ![Output Example](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0005-C-PCT.png)  


##### **Chain of Thought Prompting**

Chain of thought prompting involves asking AI to explain its reasoning step by step. This is especially useful for identifying errors and improving decision-making.  

*Prompt:*  
*“Explain your thought process step by step.”*  

![Chain of Thought Diagram](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0006-COT.png)  


##### **Tree of Thought Prompting**

Tree of thought prompting allows you to explore multiple reasoning paths simultaneously, making it valuable for abstract or complex problems.  

*Example Prompt:*  
*“Imagine three different designers are pitching their design to me. Each designer writes one step of their thinking and shares it with the group. If any expert realizes they’re wrong at any point, they leave. The question is: Generate an image that’s visually energetic, featuring art supplies and computers. Show me three suggestions in different styles from simple to detailed.”*  

![Tree of Thought Diagram](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0007-TOT.png)  

*Follow-up Prompt:*  
*“I like the first option. Expand the idea and generate three different color schemes for that concept.”*  

---

##### **Pro Tips for Prompting**

1. Combine chain-of-thought and tree-of-thought techniques by asking AI to explain its reasoning at each iteration.  
2. Use meta-prompting: Ask AI to help you generate the next prompt when you're stuck.  

---

#### AI Agents

AI agents are specialized virtual assistants designed to help with specific tasks or provide expert feedback.  

##### **Types of AI Agents**

1. **Simulation Agent (“Agent SIM”):**  
   Simulates scenarios, such as role-playing exercises.  

   *Example Prompt:*  
   *“Act as a career development training simulator. Your task is to help interns master interview skills and conduct conversations with potential managers. Support these types of conversations:  
      - Articulating strengths and skills  
      - Communicating professionally and confidently  
      - Discussing future career goals  
   Continue the role play until the intern replies with ‘JAZZ HANDS’. Then provide key takeaways from the simulation and areas for improvement.”*  

   ![Simulation Agent Example](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0008-ASM.png)  

2. **Expert Feedback Agent (“Agent X”):**  
   Acts as a tutor or consultant to provide feedback.  

   *Example Prompt:*  
   *“You’re my potential client, the VP of Advertising at a world-famous sports car company known for innovation and performance. Critique my answers, ask follow-up questions, and provide feedback until I say ‘BREAK.’ Summarize areas for improvement after the session.”*  

   ![Expert Agent Example](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0009-AGX.png)  

##### **Designing Effective AI Agents**

1. Assign a persona to the agent.  
   ![Assigning a Persona](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0010-A-AGL.png)  
2. Provide context and detail about the scenario.  
   ![Providing Context](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0010-B-AGL.png)  
3. Specify conversation types and interaction rules.  
   ![Specifying Rules](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0010-C-AGL.png)  
4. Define a stop phrase for ending interactions.  
   ![Defining a Stop Phrase](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0010-D-AGL.png)  
5. Request feedback after the interaction.  
   ![Requesting Feedback](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0010-E-AGL.png)  

AI agents can be incredibly versatile and effective when designed thoughtfully.  

-----

### Rules

| Rule                | ![No](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0011-A-NO.jpeg)              | ![Yes](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0011-B-TCK.png)                | 
| --------------------- | ---------------------- | ---------------------- |
| Rule-1: Ditch the fluff / Forget all the pleasantries                | Can you please write me a short story about a robot and a dog who go on adventure together?              | Write a short story about a robot and a dog going on an adventure               | 

