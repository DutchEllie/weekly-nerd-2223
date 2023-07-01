# Using AI for web development

I just finished an academic minor in [Web Design and Development](https://everythingweb.org/) and the Amsterdam University of Applied Sciences.
There I was introduced to many of the technologies, techniques and intricacies of web development, along with all of the beautiful people there.
My normal major is Network and Systems Engineering, so being introduced to such a different environment was very educational.
One of the technologies I had not yet used before I started this minor was generative AI, especially for coding!
It sounds like a whole different world today, a world before AI, but it's easy to forget that we haven't had ChatGPT before November 30th 2022!

In this article, I want to show my experiences and my findings with the usage of generative AI, like ChatGPT and GitHub Copilot.

## The fronteer

It's easy to forget sometimes just how new the field of (useful) generative AI really is.

OpenAI's DALL-E image generation AI model was revealed to the world just in January 2021, with a more advanced version being revealed just one year later in April 2022.
These AI models were impressive, but not even available for the general public yet.
It would take until November 2022 until API access was granted to developers for DALL-E.

The same sort of thing happened with large language models.
Anyone who was paying attention to the AI research field would have seen it coming, with OpenAI releasing blog post after blog post about GPT-3 in 2022, but the general public was caught by surprise when suddenly this previously barely-known company "OpenAI" released "ChatGPT".

Needless to say, ChatGPT took the world by storm!
It created an entirely new market just by itself and became the world's fastest growing online app ever, reaching over 100 million monthly active users after just two months of operating. [source](https://www.reuters.com/technology/chatgpt-sets-record-fastest-growing-user-base-analyst-note-2023-02-01/).
Since then, we have seen many other companies enter the generative AI market, like Google with Bard, and Meta with their Llama model.

### The tech itself

While I am not actually qualified to talk about this tech in detail, I do know the basics of what it is.
ChatGPT and similar text generation AI models are actually nothing more than a ridiculously fancy autocompletion function for text.
The AI gets fed a text, and then predicts what the next most likely "token" (often a word or a syllable) in the text.

The text that the AI takes as input is called "**context**" and the initial text that is used to start the "conversation" is called the "**prompt**".
To make effective use of this AI technology, it is vital to know these things, because your prompt is very important to accomplishing the task you want to accomplish.

## Copilot

Not long after the introduction of ChatGPT, Github Copilot was announced.
Copilot is a large language model, similar to ChatGPT, that has been specially trained on Github's collection of public repositories of code, to help with coding tasks.
It differs from ChatGPT by integrating into your IDE (like VSCode) and constantly trying to complete your code in the best way it can.
It can then suggest code for you to use, in the language you're using and often with eerily good accuracy.

Sometimes, by simply writing a comment with what you want to do it can already suggest a full function for you to use!
This tech is incredibly impressive, especially considering how much detailed coding can be.

To be fair, sometimes it's incredibly dumb as well.
I have seen Copilot do all sorts of things, from inventing fake library names to completing my comments by writing more comments going on forever.

## Hallucinations

I talked about AI sometimes inventing fake code libraries to use, well this (along with other things) has a name: hallucination.
When an AI invents fake information, lies to you or otherwise just spouts out wrong information, that's hallucination.
You must always be skeptical of the results an AI gives you, because it might seem confident with its answer, but it might be just false.

For the curious, hallucinations are a result of the nature of this sort of AI.
A large language model "knows" nothing, it only generates the most likely next token in the text.
While feeding endless data into a model like that will make it "smarter", it will always just try to complete the text it has been given.
It will generate entirely false information if it deems that the next most likely completion of the text.

## Conclusion

AI has not (yet) taken over the world, but it has taken it by storm.
From writing emails, to completing code, to teaching languages, it has changed how we work dramatically and it will continue to do so for a while.

*I wonder if I should get a Master's degree in AI now*