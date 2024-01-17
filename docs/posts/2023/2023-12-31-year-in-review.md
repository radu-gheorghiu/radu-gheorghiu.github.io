---
title: "2023 - Year in Review"
authors: 
    - radugheorghiu
date: 
    created: 2023-12-31
    updated: 2024-01-07
tags: ["generative models", "chatbots", "prompt engineering", "open-source"]
categories: ["Year in Review", "AI", "Data Engineering"]
slug: "year-in-review-2023"
---

# **2023 - A year in review**

On the 30th of November 2022, I created my ChatGPT account and started trying out the capabilities of ChatGPT, which back then represented a major disruption of what we knew as chatbots. I remember trying out in the first days the capabilities of the chatbot, mainly focusing on what we would now call "reasoning" capabilites. I tested out its flexibility, it's understanding of instructions and its ability to accomplish tasks.

<!-- more -->

But having a chatbot that could more directly reply to your questions, in natural language, did not feel like a big enough breakthrough that could change the world. It was a nice to have, but it was not a must have. It was not a game changer.

Because most of our world runs in code, I wanted to see what place I could find for this technology, in the world of software development. I wanted to see if I could use it to make my life easier, to make my work more efficient, to make my work more enjoyable.

## A spark of potential

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

## The hackathons

In late December, I stumbled upon an Instagram post that mentioned an OpenAI hackathon. I digged a bit deeper into this and noticed that [lablab.ai](https://lablab.ai/) was organizing a hackathon using the OpenAI API, in March 2023. I was excited about the opportunity and decided to sign up for it and for 2 other hackathons, which were before it, but had the same focus of building applications using LLMs.

### 1. AI21Labs Hackathon - KitchenGenie

Between the 13th and 20th of January, me and [Aurel Godoroja](https://www.linkedin.com/in/aurel-godoroja-a31026117/) formed the "LastMinute" team and signed up for the hackathon. We spent the first 3 days of the hackathon trying out the models, trying to understand the difference between an Instruct model and a simple Generate model, find out the strengths and weaknesses of each model and see what we could do with them.

I started looking online for ideas that we could use the model for, since we were not able to come up with a good idea which excited us both. At the time I was looking for some Upwork jobs so one evening I took a break and looked over the list of jobs. There was someone who was asking for an app that could take an order for a pizza, from a customer, in natural language and calculate the price of the pizza, based on the description of the pizza from the customer.

Things started to click in my head. I thought, why not a recipe generator, an app that can help you with your recipes, I know I had a ton of problems with making recipes and not letting the food spoil in my fridge. I shared my idea with Aurel and he liked it and since we had only about 3 days left in the competition, we started hacking away. We built the application so that it would simulate our bigger idea, which was to have a phone app that you could take photos of the food in your fridge to identify ingredients. Then you would pick the ingredients you want and use the app to generate a recipe for you, based on the ingredients you have in your fridge.

We gave it our all, both working full time jobs during the day and during the nights, hacking on the project. Neither of us has significant frontend experience so we decided to go with Streamlit which seemed at that time could solve all of our requirements for a user interface. The next days would prove us wrong and we spent countless hours trying to fix issues with caching variables and states so that we we interacted with the UI we wouldn't lose the flow of the application. We both ended up sleeping only 2-3 hours per night and in the last night before the submission, neither of us would get any sleep. We were absolutely all in and exhausted, but we didn't know how far we pushed ourselves.

We ended up finishing and making [our submission for the hackathon](https://lablab.ai/event/ai21-labs-hackathon/lastminute/kitchen-genie) with only 30 seconds to spare, but we were in for the judging!

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/RI-9OZ9IqIE?si=9l7Cu0y10AxTcHOo&list=PLmbqa7kiU8F95yT448zq_iH9K1RFOFRvQ&index=1&ab_channel=RaduGheorghiu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

#### On the stage

We were selected as one of the finalists and were invited to present our project during the Winner's announcement livestream.

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/2WUAtd4pTxg?si=1fedqk9i5iaDnHnT&amp;start=1173" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

Though we weren't the winner, being one of the runner ups meant a lot to us, especially since it was our first hackathon and we were building something with a technology that we were still learning about. This experience boosted our morale for the next hackathon and we were excited to see what we could do next.

Although we got close to winning, we felt that we'd won, but the coming days would show us what toll the hackathon took on us. I lost my appetite for the next 2 days and had difficulties falling asleep for the next week. Aurel also had health problems we didn't think much of back then

### 2. Cohere Hackathon - TubeTalk

Our second hackathon with lablab.ai was the Cohere Hackathon, which took place between the 27th of January and the 3rd of February.

This time though, we unfortunately struggled a bit more with finding an interesting idea, the intuition of working with LLMs in the first hackathon didn't replicate when working with Cohere's API and we struggled a bit more.

We ended up builidng an application that integrated with YouTube and analized thousands of comments from a video and generated a summary of the viewer's feedback about your video. We called it TubeTalk.

Just like the last hackathon, we worked full time jobs during the day and hacked on the project during the night. We ended up sleeping very few hours in the first days of the hackathon and we were both exhausted. We ended up [submitting the project with only 30 minutes to spare](https://lablab.ai/event/cohere-hackathon/lastminute/tubetalk), but we were happy it was over.

<div align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/eVHetu_LqzI?si=kRVnjpzmasTZ-Ozi&list=PLmbqa7kiU8F_nLetwtzrlmFLDKWs_6Aa1&index=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

This time we didn't make it to the finals, but we were happy that we were able to finish the project and submit it on time. We were also happy that we were able to get some sleep and rest a bit. But it's only when we started to notice what toll two hackathons in a row took on us, along with working full-time jobs and one of us also had a side-project and a client he was assisting.

### We needed a break

Unfortunately, when the OpenAI hackathon came, we were both exhausted and we didn't have the energy to participate in it. We were both disappointed that we couldn't participate in it, but we knew that we needed to take a break and rest a bit. We both had serious health issues, tests came out showing that we had quite a few problems and we needed to make some changes and take some rest, take care of ourselves.

I had some problems which took me a few months to recover from so I could just do my full-time job and then I could do no more. I struggled to find the energy to do some extra reading on the topic of LLMs, to keep in touch with what the community would build and what are the developments.

However, even though I was out for a while the [e/acc movement](https://en.wikipedia.org/wiki/Effective_accelerationism) was pushing for more development and more progress in this technology. It seems like nothing is going to stop progress in this space and the community will keep pushing forward.

### Getting back on track - learn/acc

Once I got healthy enough to get back into the space, I had already been following the courses that Databricks announced they would do in order to teach people how to work with LLMs.  And so starting in early June, I took part in the first cohort of students that would follow their two-part LLM course series.

#### LLM101x: LLM's - Application through Production

During this first course, the "LLM101x: LLM's - Application through Production" I learned how to:

- create and deploy Large Language Models (LLMs)
- started from the basics of Natural Language Processing (NLP) all the way to cutting-edge applications

The course was designed for technical roles like mine and covered a broad spectrum, including the emerging field of LLMOps and the societal impact of LLMs.

I got hands-on experience with the Databricks environment and the Hugging Face library. 

Specifically, I dived into:

- foundational NLP tasks
- vector databases
- multi-stage reasoning
- fine-tuning
- model selection
- model evaluation

<div align="center">
    <img src="/assets/blog_images/2023-12-31-year-in-review/llm01_certificate.png" alt="GPU Workstation" title="GPU Workstation"/>
    <figcaption><i><a href="https://courses.edx.org/certificates/b24e76ef46be4bd0914ba3e610a500f4">LLM101x certificate of completion</a></i></figcaption>
</div>

#### LLM102x: LLM's - Foundation Models from the Ground Up

In the second course, "LLM102x: LLM's - Foundation Models from the Ground Up" I went beyond the surface to understand the inner workings of Large Language Models (LLMs). Aimed at technical practitioners and scientists, the course gave me a strong technical and theoretical foundation.

Starting from the basics like the transformer block and attention mechanism, it moved to advanced topics like multi-modal LLMs. I learned about parameter-efficient fine-tuning (PEFT), quantization, and Mixture-of-Experts (MoE) approaches for efficient deployment.

The course also gave me the chance to deepen my skills in PyTorch and get hands-on experience with the Databricks environment and Hugging Face platform.

Specific topics covered included:

- the transformer architecture
- efficient fine-tuning
- optimizing deployment and training for LLMs

<div align="center">
    <img src="/assets/blog_images/2023-12-31-year-in-review/llm02_certificate.png" alt="GPU Workstation" title="GPU Workstation" />
    <figcaption><i><a href="https://courses.edx.org/certificates/a46fd8922f834b04bce3870614a71ccc">LLM102x certificate of completion</a></i></figcaption>
</div>

### Keeping up with the community

Even though I couldn't spend much time in actually coding, I still wanted to keep up with the community and that is when I started diving into Twitter more, until I found [@swyx](https://twitter.com/swyx), who was one of the most enthusiastic and active people that I have ever seen. He shared tons of ideas of new concepts and roles for software engineers, he defined the first roles and responsibilites of the new "AI Engineer", in his [Latent Space](https://www.latent.space/) post, ["The Rise of the AI Engineer"](https://www.latent.space/p/ai-engineer?).

During the summer months I expanded my Twitterverse and started following more and more people in the space, some who are more vocal, some who are more technical, some who are more business oriented. I started to get a sense of what the community is building, what are the new developments, what are the new ideas and what are the new opportunities.

Even when going on vacation and at weddings in August and September, I was still reading articles about the new architectures that are going to replace the Transformers models, new techniques for prompting like [Chain-of-Thought (CoT)](https://arxiv.org/abs/2201.11903) and [Tree-of-Thought](https://arxiv.org/pdf/2305.10601.pdf).

When everyone's wish of longer model contexts was delivered through Anthropic's 100k Claude model, we hit a new problem, the Lost-in-the-Middle problem, explored and detailed in [this article](https://arxiv.org/abs/2307.03172).

It seems that although the technology was growing in numbers, it wasn't also growing in quality and usefulness. The models were getting bigger and bigger, but the results were not getting better and better. The models were getting more and more expensive to train, but the results were not getting more and more useful.

### The end of the beginning

During the last part of the year, starting around October, I observed that the open-source community started to come closer and closer to the closed-source models. New models, smaller models, provided most of the same benefits as larger models, but at a fraction of the cost. Also, inspired by [@abacaj](https://twitter.com/abacaj)'s AI rig, I decided to look into buying my own hardware to start experimenting locally, first with fine-tuning and maybe in the future with training smaller models.

At the beginning of December, after a few weeks of research on what is the optimal hardware for my needs, but something that I could also scale up into the future, I pulled the trigger on an RTX 3090 Founder's Edition. I had to make sure that the GPU I get is compatible with the workstation I already have at home, so that I can start experimenting and growing my knowledge of working with OSS and local LLMs.

<div align="center">
    <img src="/assets/blog_images/2023-12-31-year-in-review/gpu_workstation.png" alt="GPU Workstation" title="GPU Workstation" />
    <figcaption><i>It's messy, I know, but it works</i></figcaption>
</div>

Although 2023 was a big year for the machine learning space, it is only the beginning. Anyone who has just started, we are still early. 

We've only just scratched the surface of working with multimodal models like GPT4-V, we have yet to see the full potential of small models working together in solving tasks, we've yet to expand the Agents architectures and combine them with more effective prompting techniques. We're still early and if you're a software developer, you would better start learning and experimenting with these technologies, because they will change the world.