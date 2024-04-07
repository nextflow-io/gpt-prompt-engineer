## Prompt engineer workflow with Nextflow

A Nextflow workflow to optmise GPT prompts inspired by [gpt-prompt-enginer](https://github.com/mshumer/gpt-prompt-engineer).


### Overview

Prompt engineering is kind of like alchemy. There's no clear way to predict what will work best. It's all about experimenting until you find the right prompt. `gpt-prompt-engineer` is a tool that takes this experimentation to a whole new level.

**Simply input a description of your task and some test cases, and the system will generate, test, and rank a multitude of prompts to find the ones that perform the best.**

### How to Use

1. Define your use-case and test cases. The use-case is a description of what you want the AI to do. Test cases are specific prompts that you would like the AI to respond to. For example:

```
description = "Given a prompt, generate a landing page headline." # this style of description tends to work well

test_cases = [
    {
        'prompt': 'Promoting an innovative new fitness app, Smartly',
    },
    {
        'prompt': 'Why a vegan diet is beneficial for your health',
    },
    {
        'prompt': 'Introducing a new online course on digital marketing',
    },
    {
        'prompt': 'Launching a new line of eco-friendly clothing',
    },
    {
        'prompt': 'Promoting a new travel blog focusing on budget travel',
    },
    {
        'prompt': 'Advertising a new software for efficient project management',
    },
    {
        'prompt': 'Introducing a new book on mastering Python programming',
    },
    {
        'prompt': 'Promoting a new online platform for learning languages',
    },
    {
        'prompt': 'Advertising a new service for personalized meal plans',
    },
    {
        'prompt': 'Launching a new app for mental health and mindfulness',
    }
]
```

For the classification version, your test cases should be in the format:

```
test_cases = [
    {
        'prompt': 'I had a great day!',
        'output': 'true'
    },
    {
        'prompt': 'I am feeling gloomy.',
        'output': 'false'
    },
    // add more test cases here
]
```


The test cases will be auto-generated based on the use-case description and input variables.

3. Choose how many prompts to generate. Keep in mind, this can get expensive if you generate many prompts. 10 is a good starting point.

4. Call `generate_optimal_prompt(description, test_cases, number_of_prompts)` workflow to generate a list of potential prompts, and test and rate their performance.


### Credits

This project is based on [gpt-prompt-enginer](https://github.com/mshumer/gpt-prompt-engineer) by Matt Shumer - [@mattshumer_](https://twitter.com/mattshumer_)
