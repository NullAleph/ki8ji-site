+++
title = "The Two Streams"
subtitle = "The Nature of Innovation in Amateur Radio"
date = "2026-05-10"
draft = false
tags = ["foundations", "epistemology"]
description = "Amateur radio generates both genuine innovation and persistent mythology in roughly equal measure. Understanding why requires looking at the two very different streams through which technical knowledge actually evolves."
showDescription = true
image = "TheTwoBenches.jpg"
+++
{{<figure 
src="TheTwoBenches.jpg" 
alt="Two contrasting benches"
caption="Image created by Author"
>}}

## The Nature and Pace of Change

After posting *[Engineering, Science, and Amateur Radio](https://ki8ji.org/posts/engineering-science-amateur-radio/)*, I found myself thinking more deeply about the nature of change in amateur radio over the past few decades.

So much has changed.  And perhaps, because I had been away from the hobby for so long, the changes were more visible to me than they might have been otherwise.

The modern amateur has access to tools that would have seemed almost miraculous not very long ago. Electromagnetic modeling software once reserved for serious engineering environments now runs on ordinary home computers. Tiny handheld VNAs cost less than a dinner out. SDRs place visualization and signal analysis capabilities on the bench that once belonged only to laboratories and well-funded commercial environments. [GPS-disciplined oscillators](https://ki8ji.org/posts/disciplined-by-the-sky/) quietly bring atomic-time traceability into the shack through a small antenna sitting near the window.

Information now propagates through Groups.io groups, YouTube channels, forums, Facebook groups, Discord servers, and countless online communities at extraordinary speed. Ideas move through the amateur community faster than ever before.

And that led me to an interesting question:

**How does technical knowledge actually evolve inside amateur radio?**

Because faster propagation of information is obviously not the same thing as deeper understanding. Access to better instruments is not the same thing as better reasoning about what those instruments reveal. The tools have changed dramatically. But the underlying question — how amateurs actually come to know things, and how those things spread through the community — remains surprisingly difficult.

The more I thought about it, the more I began to see two distinct streams through which technical knowledge seems to evolve.

What surprised me was realizing how old this distinction actually is.

Ancient Indian philosophical traditions wrestled deeply with the tension between received knowledge and direct experience. There is knowledge that can be transmitted through teaching, text, and formal reasoning — *propositional knowledge*. And there is knowledge that emerges only through direct encounter and lived experience — *experiential knowledge*. The debate about the relative authority of these two modes of knowing runs through centuries of Indian philosophical inquiry. The tradition's conclusion, roughly, is that neither is sufficient alone, and that genuine understanding requires both in dialogue. 

I believe this is a useful model for thinking about technical knowledge in amateur radio. Let’s look at why this might be, and examine the implications of this model.


---

## Stream One: Propositional Innovation

The first stream begins with theory.

The amateur operating in this stream understands the underlying physics well enough to derive predictions from first principles. She builds not to discover whether something will work, but to confirm what the theory already suggests. The design exists, in some essential sense, before it exists in metal.

This is fundamentally *deductive* reasoning applied to physical construction. The innovation flows from understanding to artifact.

Central Electronics comes to mind immediately as a company operating firmly in this tradition. Wes Schum’s SSB exciter designs reflected careful theoretical understanding of RF behavior rather than simple trial-and-error experimentation. This was not tinkering toward a working product, but engineering from a coherent conceptual foundation.

The same tradition runs through the lineage of serious antenna theorists and RF engineers: people who began with electromagnetic principles, derived radiation behavior mathematically, and then built to confirm predictions rather than to discover them. Warren Bruene’s later work at Collins Radio on directional couplers and RF measurement techniques belongs very much to this same world.

This stream has a particular character. It is confident in a very specific way — confident not merely that something will work, but that it understands why it will work. And that understanding enables a different kind of refinement. One can vary the theory, not merely vary the construction.

The risk, of course, is overconfidence in the model.

At the extreme edges of theoretical physics, one occasionally encounters ideas that are mathematically consistent and physically derived, yet so detached from practical experimental verification that they begin to feel almost mythic in character. A rotating cylinder with the mass of a galaxy compressed into impossible dimensions becomes, on paper, a potential time machine. The equations may permit the solution. The mathematics may even be internally elegant. But the gap between theoretical possibility and operational reality becomes so vast that one begins to wonder what kind of knowledge is actually being produced.

This does not make the work meaningless. Mathematics itself can be a profound exploratory tool. But it does highlight an important epistemological tension: a sufficiently refined model, however coherent and mathematically elegant, can nonetheless begin to drift away from empirical constraint and physical realizability.

Amateur radio operates on a far smaller and more practical scale, of course. But the underlying tension is surprisingly similar. A sufficiently elegant model can begin to feel true long before reality has fully agreed to cooperate.

The models we derive from theory are necessarily simplifications of reality. Real ground is not infinite and perfectly conducting. Real components are not ideal. Real feedlines interact with their environments in ways that simplified models do not fully capture. The theorist who forgets that the map is not the territory can be surprised, and sometimes badly, by reality.

---

## Stream Two: Experiential Innovation

The second stream begins with the workbench.

The enthusiastic tinkerer builds things. Observes what happens. Changes something. Observes again. The innovation is essentially *inductive* — patterns emerge from accumulated experience without necessarily being derived from underlying theory. The builder may not be able to explain *why* a particular configuration works better; she knows only that it does, that she has tried it multiple times, and that others who have tried it report similar results.

Much of the early antenna experimentation in amateur radio falls here. Someone tried a longer element and it seemed to work better. They told others. The practice propagated through the community. A received wisdom formed — sometimes accurate, sometimes not — without a theoretical derivation accompanying it.

This stream has its own particular character. It is humble about explanation while confident about practice. It generates an enormous amount of genuinely useful knowledge. And it is extraordinarily productive precisely because it does not wait for theoretical understanding before building and testing.

The risks, however, are real and worth naming directly.

Consider the recurring claim I came across recently that a collinear element should be 0.6λ rather than the theoretically expected 0.5λ. This idea circulates through the amateur community with considerable confidence and apparent authority. It may reflect a genuine empirical observation — real-world construction effects, the influence of nearby conductors, velocity factor considerations, or some other physical reality that the simplified theory omits. Or it may be an artifact of uncontrolled variables in the original experiments, a correlation mistaken for causation, or a measurement taken under conditions that do not generalize.

The claim propagates either way. Received wisdom does not come with error bars attached.

Certain ideas develop extraordinary persistence inside amateur radio culture. A vertical “radiates poorly in all directions.” An antenna tuner somehow “tunes the antenna.” A feedline is declared “lossless” because the SWR meter in the shack looks acceptable.

Other ideas persist long after the original context that justified them has been forgotten entirely. A particular balun ratio becomes universal advice. A feedline length acquires mystical significance. A construction technique becomes folklore through repetition alone.

Sometimes these ideas contain a core of truth that has been simplified beyond recognition. Sometimes they arise from real empirical observations made under narrow conditions and then generalized too broadly. And sometimes they are simply repeated often enough that repetition itself begins to substitute for validation.

The interesting question is not whether such beliefs exist. Every technical culture accumulates them. The interesting question is how they propagate, why some persist even after contradictory evidence becomes widely available, and why others eventually collapse under better models and better measurement.

This is not a criticism of experiential innovation as a method. It is an honest accounting of what the method can reveal, and what it cannot reliably guarantee.

---

## The Interaction

The really rich territory lies not in either stream alone, but in the interplay between them.

Because the two streams do not operate independently. They feed each other — sometimes productively, sometimes not.

Experiential innovation often precedes propositional understanding. The tinkerer discovers something real that the theorist then explains. The history of science is full of this pattern: empirical observation comes first; theoretical framework catches up later, validates the observation, and enables further propositional innovation that the pure tinkerer could not have reached alone. For example, experimental observations of black body radiation stubbornly refused to match the predictions of classical physics, forcing theory itself to evolve. What began as an empirical anomaly eventually became one of the doorways into quantum mechanics.  

Some of the most important insights in antenna design arrived this way — builders noticed behavior that theory eventually accounted for and generalized.

But propositional innovation sometimes gets stuck without experiential feedback. The theorist's model makes predictions that turn out to be sensitive to variables the model did not capture — real ground, real weather, real construction tolerances, real component variations. The tinkerer's empirical feedback corrects the theory's blind spots. Without that correction, the theory circles around itself, refining its internal consistency while drifting further away from physical reality.

And the most powerful innovators work both streams simultaneously.

Model before build — but validate the model against real-world results and let discrepancies feed back into the model. Use electromagnetic simulation software before construction, but follow that with propagation testing, antenna analyzer measurements, and genuine willingness to revise the model when reality disagrees. The cycle is not theory-then-practice or practice-then-theory. Ideally, it is theory-and-practice, iterating together, each constraining and informing the other.

---

## An Epistemological Observation

What I am pointing at has a deeper structure.

The two streams represent two fundamentally different relationships between knowledge and action.

In Stream One, knowledge precedes and generates action. You understand why something will work before you build it. The risk is that the model is incomplete and reality surprises you.

In Stream Two, action precedes and generates knowledge. You build before you fully understand, and understanding — to whatever degree it arrives — emerges from the building. The risk is that you misread the results, confuse correlation with causation, or generalize from an uncontrolled experiment.

Neither stream is epistemologically privileged. Both have generated genuine innovation. Both have generated persistent myths. The question is not which stream is better, but whether the practitioner understands which stream she is operating in at any given moment — and whether she is honest about what that stream can and cannot guarantee.

This tension is not unique to amateur radio. It is a deep and recurring feature of human knowing across domains.

The ancient Indian philosophers who wrestled with these two modes of knowledge would probably have found amateur radio entirely familiar: a community perpetually negotiating between received propositional knowledge and direct experiential encounter, never fully able to reduce one to the other, and perhaps healthiest when both remain in active dialogue.

---

## The Community That Results

Amateur radio's particular institutional structure makes this interplay especially visible.

The Extra Class license demands theoretical knowledge — but it does not require the ability to derive anything from first principles. It requires the ability to recognize correct answers. This produces a licensed population with genuinely varying depths of theoretical understanding, all nominally credentialed to the same level. Some Extra Class operators could derive antenna radiation patterns from Maxwell's equations. Many could not, and have no need to.

The experimental tradition implicit in amateur radio — the freedom to build and try things that distinguishes the amateur license from a consumer electronics relationship with radio — encourages Stream Two activity across the entire population regardless of theoretical depth.

The result is a community that generates both genuine innovation and persistent mythology in roughly equal measure, with limited mechanisms for distinguishing between them. *QST* publishes both the brilliant theoretical derivation and the "I tried this and it seemed to work" report, often with similar levels of apparent authority. The forum post that cites careful controlled measurement sits alongside the forum post that cites tradition and personal impression. Both can be difficult to distinguish at first reading.

This is not a criticism of the community. It is simply what happens when theory, experimentation, tradition, intuition, and received wisdom all evolve together inside the same living technical culture.

And perhaps — this is the thought I find most interesting — it is also what keeps the inquiry genuinely alive.

A community that has resolved all its foundational questions and established clean mechanisms for distinguishing innovation from myth would be a community with less to wonder about. The productive uncertainty is not merely a liability. It is part of what makes amateur radio, at its best, an ongoing investigation rather than a finished body of received practice.

---

## The Deeper Question

The tools will continue to improve.

Information will continue to propagate faster.

But the deeper question — how to know what we actually know, how to distinguish the map from the territory, how to hold theoretical understanding and direct experience in productive dialogue — will remain.

That question does not resolve with better instruments.

It resolves, to whatever degree it resolves, with better thinking.

Which is, in the end, what this series of essays is attempting to practice.

---

## Further Reading

* James Clerk Maxwell — A Dynamical Theory of the Electromagnetic Field
* Warren B. Bruene, W0TTK — "An Inside Picture of Directional Wattmeters," QST, April 1959. (The foundational analysis of Monimatch-type and Bruene directional couplers; forward and reflected power measurement from first principles.)
* Central Electronics' history of innovation, See Dominic (Nick) Tusa's "Wes Schum, Amateur Radio's Unsung Hero"
* NEC and Method of Moments antenna modeling literature
* Karl Popper — Conjectures and Refutations
* Thomas Kuhn — The Structure of Scientific Revolutions
* Richard Feynman — The Character of Physical Law
* Frank Tipler — “Rotating Cylinders and the Possibility of Global Causality Violation” (Physical Review D, 1974)
(The famous “Tipler Cylinder” paper: a fascinating example of mathematically rigorous physics operating at the edge of physical realizability.)

---

## Addendum: A Third Stream Powered by Serendipity?
Shortly after this essay was posted, my friend Jeff Bauman, W8KZW, wrote with a thought:
	
*Shear accident — the third stream?*
	
Jeff was recalling the story of Bob Gore, who in 1969 was attempting to stretch heated rods of PTFE slowly to create a plumber's tape. After repeated failures, he became frustrated and gave the rod a sudden, sharp yank. Instead of breaking, the material stretched nearly 1,000%, producing a strong, microporous structure that was breathable yet waterproof. That discovery became Gore-Tex — and the pun in Jeff's question is entirely intentional.
	
It is a fair challenge to the two-stream model.
	
The Gore-Tex story does not fit cleanly into either stream. It was not deduced from theory. It was not the result of systematic empirical variation. It was an accident, born of frustration, that happened to produce something remarkable.
	
And yet — the accident alone was not sufficient. Bob Gore recognized what he had found, understood it well enough to patent it, and built a company around it. That recognition required propositional knowledge. Without understanding polymer chemistry, the unexpected stretch was simply a broken experiment. The serendipity provided the spark; Stream One carried it forward.
	
In amateur radio, the serendipitous stream might be the most honest description of how some of our most persistent mythology originates. An operator makes a wiring error, creates an unintended configuration, notices surprisingly good results, and tells others. Pure accident — but what happens next determines everything. Does someone model it and understand why it worked? Or does it propagate as received wisdom, untethered from its accidental origins?
	
Perhaps serendipity is less a third stream than a hidden source that feeds both. The question of which stream carries the discovery forward — and whether anyone stops to ask why the accident worked — may be one of the most important epistemological question of all.
	
Jeff, thank you for the *shear* insight!
