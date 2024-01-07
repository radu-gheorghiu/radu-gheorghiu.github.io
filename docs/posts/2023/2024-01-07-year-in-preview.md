---
title: "2023 - Year in Review"
authors: 
    - radugheorghiu
date: 
    created: 2023-12-31
    updated: 2024-01-07
tags: []
categories: ["Year in Review", "AI", "Data Engineering"]
slug: "year-in-review-2023"
---

# **2023 - A year in review**

On the 30th of November 2022, I created my ChatGPT account and started trying out the capabilities of ChatGPT, which back then represented a major disruption of what we knew as chatbots. I remember trying out in the first days the capabilities of the chatbot, mainly focusing on what we would now call "reasoning" capabilites. I tested out its flexibility, it's understanding of instructions and its ability to accomplish tasks.

<!--more-->

But having a chatbot that could more directly reply to your questions, in natural language, did not feel like a big enough breakthrough that could change the world. It was a nice to have, but it was not a must have. It was not a game changer.

Because most of our world runs in code, I wanted to see what place I could find for this technology, in the world of software development. I wanted to see if I could use it to make my life easier, to make my work more efficient, to make my work more enjoyable.

### A spark of potential

I remember when I gave the first instructions to ChatGPT to process a certain text and respond in a certain way, using a JSON schema which I had gave it and instructed it to fill in the appropriate values.

> I want you to process this text and reply with the following JSON schema? The text is: "My name is John and I am 30 years old. I live in New York, on 5th Avenue, number 10.". The JSON schema is:

```json
{
    "name": <name>,
    "age": <age>,
    "address": {
        "street": <street address>,
        "number": <street number>,
        "city": <city>,
        "country": <country>
    }
}
```

The instructions felt "sloppy" and unorganized, requirements not clearly defined, as we were used to in the world of software development. But the chatbot was able to understand what I wanted and to deliver the results I was expecting. The chatbot was able to deliver the results I was expecting, without any problems, without any errors, without any delays.

```
{
    "name": "John",
    "age": 30,
    "address": {
        "street": "5th Avenue",
        "number": 10,
        "city": "New York",
        "country": "USA"
    }
}
```

That is when I could feel a change that would happen. I started fiddling with the chatbot even more, to find its strengths and its weaknesses. Many people were saying that the bot is a great replacement for Google and doing a search, but that its reasoning capabilities are not that great, that we are still far away from such a technology to replace human reasoning.

But just because it wasn't able to do something you expected, when you gave it short instructions, wasn't something that convinced me of its inability to "reason". The JSON examples proved me wrong, it gave me a sense of what we would end up calling "prompt engineering". I discovered on my own that if you do ask the bot the right question using the proper wording and instructions, it would be able to do what you wanted it to do.

I remember people asking the bot for code and it would sometimes be a hit or miss, thus ending up by discrediting it completely and saying that it is not a good replacement for a software developer. But I knew that it was just a matter of time until we would be able to use it to write code for us. I felt that we just need to find a way to ask the bot to give us the right information or for the tecnology to make a small incremental improvement and we would get better models, better chatbots, better results. I saw a spark of potential and decided to dive deeper into the next opportunity that would come my way.

### The hackathons

In late December, I stumbled upon an Instagram post that mentioned an OpenAI hackathon. I digged a bit deeper into this and noticed that [lablab.ai](lablab.ai) was organizing a hackathon using the OpenAI API, in March 2023. I was excited about the opportunity and decided to sign up for it and for 2 other hackathons, which were before it, but had the same focus of building applications using LLMs.

#### 1. AI21Labs Hackathon - KitchenGenie

Between the 13th and 20th of January, me and [Aurel Godoroja](https://www.linkedin.com/in/aurel-godoroja-a31026117/) formed the "LastMinute" team and signed up for the hackathon. We spent the first 3 days of the hackathon trying out the models, trying to understand the difference between an Instruct model and a simple Generate model, find out the strengths and weaknesses of each model and see what we could do with them.

I started looking online for ideas that we could use the model for, since we were not able to come up with a good idea which excited us both. At the time I was looking for some Upwork jobs so one evening I took a break and looked over the list of jobs. There was someone who was asking for an app that could take an order for a pizza, from a customer, in natural language and calculate the price of the pizza, based on the description of the pizza from the customer.

Things started to click in my head. I thought, why not a recipe generator, an app that can help you with your recipes, I know I had a ton of problems with making recipes and not letting the food spoil in my fridge. I shared my idea with Aurel and he liked it and since we had only about 3 days left in the competition, we started hacking away.

We ended up finishing and making [our submission for the hackathon](https://lablab.ai/event/ai21-labs-hackathon/lastminute/kitchen-genie) with only 30 seconds to spare, but we were in for the judging!

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/RI-9OZ9IqIE?si=9l7Cu0y10AxTcHOo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>