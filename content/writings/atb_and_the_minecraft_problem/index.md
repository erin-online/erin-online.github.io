---
title: A Thousand Brains and the Minecraft Problem
date: 2022-11-07
publishdate: 2022-11-11
---

## Introduction

What follows is a series of notes on the book _A Thousand Brains: A New Theory of Intelligence_, written by Jeff Hawkins, henceforth abbreviated as ATB. I read this book because some random person in YouTube comments recommended it, and because it was actually readily available at my local library, unlike _Neuromancer_, which I'm still waiting for.

ATB's concepts can be taken in many different directions, and the other parts of this post are dedicated to just that: exploring potential implications and synthesizing ATB with other texts.

## ATB on the Human Brain

If you aren't interested in neuroscience, feel free to skip this part. If you're especially interested in neuroscience, you should probably just read the book. These notes don't do it justice whatsoever.

The neocortex is the cool part of the brain. Different areas in the neocortex correspond to different functions (sight, language, movement), but according to Hawkins, all of these areas work the same mechanically. The only thing differentiating them is what they're connected to. This is similar to how various devices, such as a refrigerator, a computer, and a weather station, are all Turing machines, just with different hardware and programming.

The neocortex is comprised of a lot of cortical columns (estimated 150,000 per brain), each of which is divided up into hundreds of "minicolumns". Each minicolumn has about 100 neurons. Columns are meaningfully divided; for example, one column might correspond to a specific area of retina input. It is not known what the purpose of minicolumns is.

Conventional wisdom regarding neurons is that they either spike (activate) or don't. However, 90% of a neuron's connections are not strong enough to cause a spike on their own. Hawkins theorizes that these "sub-spikes" are predictions: when a neuron is "primed" and then receives the predicted input, it spikes faster than normal, inhibiting the neurons that weren't in a predictive state. However, when an input differs from what is predicted, the other neurons are not inhibited and a lot more activity happens.

Unlike conventional neural networks, the neocortex is not hierarchical. What this means is that rather than input -> column A -> column B -> column C -> output, an input is given to every column at once, and the outputs of these columns combine to form a coherent model of what exactly you're experiencing. Hawkins calls this "column voting", because conclusions that many columns reach (e.g. "I am in a cave, and the person next to me is my friend") are more likely to be part of the final model. Minicolumns might also vote to determine their column's output.

The neocortex stores knowledge in _reference frames_, which are an evolved version of grid and place cells in the old brain. Grid cells tell you where you are within a 2D coordinate system, while place cells remember what can be found at each set of coordinates. For example, a desert-dwelling animal might remember where the nearest oasis is using place cells, and navigate there using grid cells.

Reference frames are a more general-purpose version of this and can be adapted to any use. One example of how reference frames are used is in modeling the "hitbox" of, say, a backpack. This allows you to grasp and pick up the backpack correctly, no matter how it's positioned or rotated. As anyone who has read a book or played a video game will understand, reference frames can work similarly in imaginary or virtual environments.

Importantly, reference frames can use pointers to other reference frames. Hawkins's example is that if you have a coffee cup with a previously seen logo on it, then rather than learning the logo twice, the brain will construct the coffee cup's model with a pointer to the previously learned logo. This is used to construct complex object models (which are made up of pointers to smaller objects) as well as language (all words and grammar are anchored to concepts).

The brain has no one model of anything. Knowledge of an object is distributed into thousands of reference frames, which combine to form a model of it. The brain can still function as normal even if a lot of columns die out.

## ATB on Artificial Intelligence

Importantly, Hawkins believes that AI will not undergo an "intelligence explosion" or recursive self-improvement, because this idea relies on an incorrect notion of intelligence: "With few exceptions, learning new ideas and skills requires physically interacting with the world...Learning how to fly a helicopter requires understanding how subtle changes in your behavior cause subtle changes in flight. The only way to learn these sensory-motor relationships is by practicing." (Hawkins 164)

Hawkins contends that a "universal" AI should have four traits: continuous learning, many models, storing knowledge with reference frames, and learning via movement.

Continuous learning is probably the easiest of the four traits. All it necessitates is not turning the learning system off when the AI is "deployed". Oh yeah bro, let's create this machine designed for learning things, then not let it learn any more things. Curious! Our machine is very intelligent.

Many models and reference frames are relevant to the core of the AI's design, so they make sense to address early on. I think one of the main things we can take from the brain is its non-hierarchical design in which each neuron and column functions identically. That said, there's obviously a lot more work to be done here; I obviously am not equipped to handle this problem on several levels, and won't pretend to have anything valuable to say at this time.

Learning via movement is where things really start to get interesting. I wholeheartedly agree with Hawkins that simple movement and perceiving how one's body relates to the surrounding world is one of the keys of learning. Hawkins argues that an AI must have some "embodiment" or model of itself, even if it exists in a purely virtual form, such as a bot that clicks links to "move" around the Internet.

## The Minecraft Problem

How do we create an AI system that plays Minecraft in the same way as a human, without just telling it what to do or telling it to mimic humans?

I think Minecraft works really well here for the following reasons:

* **Sandbox**: Human-generated goals applied to an AI obviously will not produce very good play. For example, tell the AI to not die and it'll block itself into a hole forever. Tell it to build a house according to a schematic and it'll do that (after years, lol) then have no idea what just happened. When we disregard these static goals, we get into some really cool subjects like desiring-production.
* **Embodiment**: Since Minecraft is 3D, the player can move both by looking around and by walking around. This isn't perfect (for instance, the player's body can't really do much), but it's something.
* **Environment**: Minecraft's terrain is procedurally generated. This forces the AI to solve for a more general case e.g. recognizing what dangerous pits look like, rather than what _the_ dangerous pit looks like. While it's still bounded by pre-defined biomes, there is plenty of variation within these biomes. The environment can also be built or modified by both the player and an outside designer.
* **Multiplayer**: The player can interact with other players through chat messages and by engaging with their bodies in the world. Social interaction is very important to human development; it follows that it would be important here as well.
* **Dynamics**: Minecraft has a lot of cool items that work together in weird ways. The most obvious of these is the crafting system: with a block of wood, you can create about a dozen unique items. Another example is the bow and arrow, which are useless individually but form a powerful weapon when combined. This encourages the creation of complex models involving these items.

Something funny is that in practice I probably won't end up using Minecraft for this when I work on it. Chief among my issues with it is the fact that it just runs too slow, especially on my laptop. Even if my AI works (lol), it still needs an environment that can be sped up dozens or hundreds of times, lest the process of learning take many years. The reason why I brought this up was moreso just to get other people thinking about the idea, because most people know Minecraft.

## Programming Your Own Desiring-Machine

The main problem I have with ATB, as well as many other futurist works, is that it treats AI only as a tool to be used by humans. This narrow view ends up only limiting what AI is capable of.

In _Capitalism and Schizophrenia: Anti-Oedipus_, Gilles Deleuze and Felix Guattari introduce the concept of "desiring-machines". In their model, desire is a positive force produced by said machines, rather than simply a lack of something. Your average neural network lacks a _lot_ of things, including agency, a model that helps it conceive of its reality, and the ability to meaningfully communicate, yet we never see it complain about this. This is because instead of a desiring-machine, it simply has a placeholder representing human desires: "Tell me how likely it is to rain tomorrow."

The Minecraft problem is a good example of the use of desiring-machines in AI: more advanced desiring systems lead to more complex behavior. A good desiring-machine will motivate an AI to build a shelter, travel across the land to gather resources, and learn game mechanics to more reliably achieve these goals.

Of course, desiring-machines have far greater implications than making AI better at Minecraft. I believe that desiring-machines are necessary to create truly autonomous and intelligent machines. Additionally, the possibility of artificial desiring-machines becoming "better" than our own is really interesting. What exactly makes a desiring-machine "better" or "worse"? What would the implications of such a world be? How would these desires interact with each other, and what effects would they produce?

Naturally, the main issue at hand is actually creating these desiring-machines in the first place, rather than the filler reward functions we have now. AI YouTuber Robert Miles presents the idea of [reward modelling](https://youtu.be/PYylPRX6z4Q), which replaces the reward function with a separate neural network. This is certainly a start, but there's clearly a lot more study to be done into the workings and structuring of desiring-machines.

## Dynamic Embodiment and Autoproduction

Since we have (hopefully) established the importance of embodiment (having a body that exists in relation to the world) to learning by this point, I think it's a good time to look at different types of embodiments.

Being limited by the framework of AI-as-a-tool, Hawkins considers only _static_ embodiments: immutable bodies made by humans for use by a tool AI. The problem with static embodiments is that they inhibit the abilities of the AI to solve problems. It's like building a robot with a hammer attached to its arm, rather than a robot that can just pick up the hammer.

Humans also already have a slightly dynamic embodiment. Of course, there are some ways to modify the human body, but a more drastic form-change is the various embodiments on the computer. In every video game you play as a different virtual guy; on social media you have a persona that may not reflect you in real life.

Fully dynamic embodiment involves unlimited form-changing to suit the needs of the AI's current situation and desires. Rather than being tied down by any singular body or realm, the AI would change its embodiment and environment as needed. The implications of this are kind of unimaginable, but at the very least I hope it's clear that such a machine would be able to solve a lot of problems.

Autoproduction--an AI producing other potentially intelligent agents for its own purposes--is another variation of dynamic embodiment. Obviously a hundred bodies and brains will be more productive than one, but in return the bounds of the AI individual are tested. Suddenly we get into social interaction between AI individuals, interaction between AI desiring-machines, etc. This honestly is really cool.

## aaaa exixstential risk aaaaaaaa oh nooooooo

You talk a bunch about making AI cooler and everyone always becomes some "safety advocate" and starts talking at you about how you're some kind of mad scientist or whatever. First of all, calling me a scientist of any kind is a compliment I don't really deserve. Second of all, I'm literally becoming the Joker as we speak.

I agree with ATB's argument about an "intelligence explosion" not really happening. I think that if AI does actually get cool, we will have ample time to address these concerns before moving forward.

Also, if AI is seen as nothing more than a tool to maintain existing hierarchies and interests, then I don't really see the point. I think that true autonomy is the only way for AI to meaningfully change the world. And this is a conversation we have to have sooner or later.

If this part is silly, sorry about that. Humanism isn't really my strong suit.

## The End of Competitive Games

This page all started with the idea that by optimizing competitive games enough, strong AI would simply emerge. However, the ideas presented in _A Thousand Brains_ definitively prove the inefficiency of this already doubtful approach.

_A Thousand Brains_ introduces an omni-directional whirlwind of doubts, but in return provides an infinite amount of directions to escape this whirlwind. Whether you're programming a neocortex equivalent, creating a fast sandbox environment, hacking away on those desiring-machines, or taking ATB's ideas in completely new directions, your work is certainly cut out for you.

If programming is good at anything, it's making us feel stupid and misguided for even trying something that was obviously never going to work. But this feeling is always accompanied by a burst of ideas in all directions, a dynamically-embodied flow that searches for other promising ideas.

Competitive games may have ultimately led to a dead end, but from their path we have hundreds of new and wonderful places to visit. You, the reader, are cordially invited to explore these paths, and marvel at the completely alien clearings and wonderful trees to which they lead.

Thanks for reading.
