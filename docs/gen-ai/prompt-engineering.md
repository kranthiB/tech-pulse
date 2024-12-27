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
      * [Designing a Prompt: A 5-Step Framework](designing-a-prompt-a-5-step-framework)
        * [1. Task](#1-task)
        * [2. Context](#2-context)
        * [3. References](#3-references)
        * [4. Evaluate](#4-evaluate)
        * [5. Iterate](#5-iterate)
            * [Mnemonic to Remember Iteration Methods](#mnemonic-to-remember-iteration-methods)
        * [Mnemonic to Remember the Framework](#mnemonic-to-remember-the-framework)
      * [Multimodal Prompting](#multimodal-prompting)
        * [Examples of Multimodal Usage](l#examples-of-multimodal-usage)
      * [Major Issues When Using AI Tools](#major-issues-when-using-ai-tools)
        * [1. Hallucinations](#1-hallucinations)
        * [2. Biases](#2-biases)
        * [Mitigating Issues](#mitigating-issues)
      * [Using AI Responsibly](#using-ai-responsibly)
      * [Designing Prompts for Everyday Work Tasks](#designing-prompts-for-everyday-work-tasks)
        * [Prompt Library](#prompt-library)
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

### Designing Prompts for Everyday Work Tasks

Creating prompts for daily work tasks involves applying the 5-step framework and iteration methods effectively. Below are examples of common use cases:

#### Prompt Library

- **Writing Emails**
   Example:  
   *"I'm a gym manager, and we have a new gym schedule. Write an email informing our staff of the new schedule. Highlight the fact that the M/W/F Cardio Blast class changed from 7:00 AM to 6:00 AM. Make the email professional and friendly, and short so that readers can skim it quickly."*  

![WEM](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0002-WEM.png)

   For straightforward emails, simplicity suffices. However, for more critical communications (e.g., essays, articles, newsletters), focus on tone and word choice. For example:
   - Instead of: *"Write a casual summary."*
   - Use: *"Write a summary in a friendly, easy-to-understand tone, like explaining to a curious friend."*
   You can also provide references (e.g., previous emails or articles) to help match the tone and style.

- **Creating Timelines and Plans**
   Example:  
   *"I'm a marketer for a well-known video game producer specializing in immersive story-based online games. I'm planning the launch of a new medieval fantasy role-playing game about a young protagonist searching for their missing partner. The primary audience is young adults. The game is in its final development stages, and I need help creating a timeline for the year leading up to the launch. Also, suggest pre-launch ideas to generate buzz."

![CTP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0003-CTP.png)

- **Staff Scheduling**
   Example:  
   *"I have 10 employees. Their employee numbers are 1 through 10. Create a table that tracks weekly staffing. Create columns for day, name, and shift (morning or afternoon). Morning shift and 2 employees scheduled for the afternoon shift
   Employees should not be scheduled for a morning shift on the following day after they were scheduled for an afternoon shift.
   Employees should not be scheduled for both the morning and afternoon shifts on the same day.
   Every employee should have roughly the same number of total shifts per week"

![SSD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/prompt-engineering/0004-SSD.png)

-----
