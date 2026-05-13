+++
title = "Disciplined by the Sky:"
subtitle = "A Look at the DXPatrol GPSDO V3"
date = "2026-05-07"
draft = false
tags = ["gear"]
description = "A reflective inquiry into what a GPSDO means physically and operationally — and why disciplining a local oscillator to GPS signals is a profound act of measurement."
showDescription = true
image = "kevin-stadnyk-HsqBGASgXJA-unsplash.jpg"
+++
{{< figure 
	src="kevin-stadnyk-HsqBGASgXJA-unsplash.jpg" 
	alt="Close up of a compass"
	caption="Photo by <a href='ttps://unsplash.com/@obruta?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'>Kevin Stadnyk</a> on <a href='https://unsplash.com/photos/a-satellite-satellite-flying-over-the-earth-HsqBGASgXJA?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'>Unsplash</a>"
>}}
	
> *"What is time?  
> If no one asks me, I know what it is.  
> If I wish to explain it to him who asks, I do not know."*  
> — Augustine of Hippo, *Confessions*, 397 AD
	
## Prologue: A Small Box, A Large Question

The DXPatrol GPSDO V3, from DXPatrol, a small Portuguese manufacturer, is a low-cost GPS-disciplined oscillator. It uses an internal U-blox 7N GPS receiver to discipline its 10 MHz TCXO and provides a 1 PPS output along with four additional LVCMOS outputs. Each output can be independently configured from the front panel rotary encoder to any frequency between 350 kHz and 350 MHz.

The outputs appear on four SMA connectors on the rear panel, with the 1 PPS output available on a front panel SMA connector. There is a small display, a control knob, Wi-Fi connectivity, app control, and NMEA data output. The unit ships with a GPS antenna on a three-meter cable that will probably end up on a window ledge or somewhere near the roof.

All of this lives inside a remarkably small metal enclosure measuring just 84 mm × 71 mm × 25 mm. Power requirements are modest: 6 to 14 volts DC at roughly 350 mA.

The specifications are impressive. Low phase noise. Less than 0.7 picoseconds RMS jitter. Adjustable output phase from 0 to 360 degrees. One millihertz frequency resolution. NMEA data over USB-C that can be fed into programs like u-center or Dimension 4 to synchronize a computer clock to GPS time.

All this from a box costing less than a moderately decent dinner for two.

But the specification sheet does not really tell you what this thing is.

To understand that, you end up asking a stranger question: what does it actually mean to discipline a local oscillator using timing signals that only work because Einstein was right?

---

## The Problem of Local Time

Before we examine the solution, we must understand the context.

An oscillator oscillates. At its simplest, it is a resonant structure — a quartz crystal, a tuned LC tank, a ceramic resonator — that prefers to vibrate at a particular frequency. You excite it; it rings. You sustain that ringing with an amplifier feeding back a portion of its own output. The system finds its natural frequency and locks onto it like a dog finding a scent.

This is the foundation of every radio in the shack. The transmitter's carrier frequency. The VFO. The injection frequency of every superheterodyne receiver ever built. The sample clock of your SDR. Somewhere underneath almost every modern electronic system, something is oscillating steadily away.

Quartz crystals are piezoelectric. They move between the mechanical and electrical worlds with remarkable precision. Electrically excite the crystal and it vibrates mechanically. Let it vibrate mechanically and it produces an electrical signal.

**The trouble is that *vibration is not invariant*.**

Real physical things change. Temperature changes them. Mechanical stress changes them. Time changes them. And when the physical structure changes, even slightly, the resonant frequency changes with it.

The resonant frequency of a quartz crystal depends with astonishing precision on its physical dimensions. Change those dimensions by a tiny amount and the frequency shifts. A temperature coefficient of a few parts per million per degree Celsius is entirely typical. On a calm day, your oscillator might drift tens of hertz at 10 MHz simply because a cloud passed overhead and the room temperature changed by two degrees. Turn on the transmitter, add heat from the finals, and the drift becomes even more obvious.

A century ago, early radio amateurs operated with very little frequency consciousness. Their wavelengths were mostly determined by the behavior of spark gaps, coils, and tuned circuits. The medium tolerated a surprising amount of imprecision.

That changed as the spectrum filled and interference became harder to ignore. Frequency stability stopped being a luxury and became part of good operating practice. Amateurs learned to hold frequency. They built temperature-compensated oscillators. They let rigs warm up for half an hour before operating. They learned the peculiar drift behavior of their equipment and compensated almost instinctively with the clarifier.

This was the era of local time.

You calibrated your oscillator against whatever reference you could find. Maybe WWV or WWVH. Maybe, if you were fortunate, a secondary frequency standard at a university or laboratory. And then you hoped the oscillator behaved itself afterward.

Before GPS discipline became practical, serious frequency standards mostly lived in laboratories, observatories, and national standards institutions. Rubidium references existed, along with cesium beam standards and hydrogen masers, but they were expensive instruments. Often large, power-hungry, and far beyond the reach of most amateurs.

The deeper problem is that local time slowly and inevitably drifts away from itself.

Local time is always, in some sense, *lost*. Every oscillator ages. Every oscillator drifts. Every oscillator is a small clock running in thermal and mechanical isolation from the rest of the universe, gradually losing its argument with entropy.

---

## The Oven and the Crystal

Engineers never really solved oscillator drift. They just came up with increasingly sophisticated ways to manage it.

One approach is the TCXO, the Temperature Compensated Crystal Oscillator. A TCXO tries to anticipate how the crystal will drift as temperature changes and continuously nudges the oscillator in the opposite direction. Done well, it works surprisingly well. A decent TCXO can hold frequency to within a fraction of a part per million over a wide temperature range.

Good enough for many things. Not good enough if you really care about frequency reference.

The Oven Controlled Crystal Oscillator, the OCXO, takes a more stubborn approach. Instead of compensating for temperature changes, it tries to prevent them from happening in the first place.

The crystal sits inside a tiny heated enclosure held at a carefully controlled temperature, usually somewhere around 70 to 85 degrees Celsius. A thermistor monitors the temperature, a control circuit adjusts the heater, and the whole little system works continuously to keep the crystal in a stable thermal environment.

In that warm isolated world, the crystal becomes remarkably consistent.

A good OCXO can hold frequency astonishingly well over short periods of time. Errors become measured in tiny fractions of a hertz. Over seconds or minutes, an OCXO is a genuinely impressive timekeeper.

But “short-term” is the important phrase.

Over longer periods, even the best crystal slowly drifts. The quartz ages. Mechanical stresses relax. Tiny physical changes accumulate over months and years. None of this happens quickly, but eventually even a very good OCXO begins to wander.

For most radio operating, the drift is insignificant. For weak-signal digital work, precision frequency measurement, or systems that need long-term synchronization, it begins to matter.

The OCXO is a kind of local hero. Extremely stable over short periods, slowly drifting over longer ones. Precise, but not truly accurate.

It knows exactly what time it thinks it is while gradually arguing with the rest of the world about what time it actually is.

---

## The Global Reference and the Relativistic Clock

Now we have to leave the shack and go to orbit.

GPS, or more precisely GNSS when we include its Russian, European, and Chinese cousins, is usually described as a navigation system. But its real foundation is timekeeping.

That inversion is worth pondering for a moment.

GPS does not really use time to determine position. It uses extraordinarily precise time measurement, and position falls out of the math almost as a side effect.

Each satellite carries multiple atomic clocks, usually rubidium and cesium standards, with astonishing long-term stability. The satellite continuously broadcasts precisely timestamped signals. Your receiver listens to several satellites at once and measures how long each signal took to arrive.

At the speed of light, even tiny timing errors matter. A nanosecond corresponds to roughly 30 centimeters of distance.

With signals from enough satellites, the receiver can solve for latitude, longitude, altitude, and its own clock error simultaneously. Position emerges from timing.

And as a byproduct, your receiver now knows what time it is with extraordinary precision.

The satellite clocks themselves are synchronized to Coordinated Universal Time, UTC, maintained by an international ensemble of atomic clocks distributed across national standards laboratories. NIST in the United States. PTB in Germany. Similar institutions around the world.

Eventually, that chain reaches your bench.

Atomic clock → satellite → GPS signal → receiver → 1 PPS pulse → discipline loop → oscillator → your shack.

But this is where the story becomes genuinely strange.

GPS only works because the relativistic corrections are real.

Not approximate. Not theoretical. Not engineering folklore. Real.

**General relativity** tells us that clocks run at different rates in different gravitational fields. A clock deeper in Earth’s gravitational well runs slightly slower than one farther away. GPS satellites orbit roughly 20,000 kilometers above the Earth, where gravity is weaker, so their clocks naturally run fast relative to clocks on the ground.

**Special relativity** pushes the other direction. The satellites are moving quickly enough that their motion causes their clocks to run slightly slow.

The two effects do not cancel. Together, they produce a net timing error of about 38 microseconds per day.

That sounds tiny until you remember that light travels almost 300 meters in a single microsecond. Left uncorrected, the navigation errors would accumulate into kilometers within a day.

The engineers designing GPS knew this from the beginning. The satellite clocks were intentionally offset before launch so that once in orbit, with relativistic effects included, they would tick at the correct rate as seen from Earth.

Without those corrections, GPS simply would not work.

That is the part people often miss.

Every time your GPSDO locks to the satellites overhead, it is quietly depending on Einstein being right.

The 1 PPS pulse arriving at your oscillator is accurate because the system accounts for gravitational time dilation and relativistic motion in real time. The timing reference on your bench ultimately traces back to atomic clocks in orbit whose frequencies have already been corrected for the curvature of spacetime around the Earth.

And somehow, all of this arrives at your shack through a little patch antenna sitting near the window.

---

## The Discipline Loop — Local Meets Global

So how does the GPSDO actually perform the reconciliation between local precision and global accuracy?

The GPS receiver produces a 1 PPS signal: one sharply defined pulse every second, aligned to UTC with remarkable precision. But the pulse only tells you *when* the second begins. By itself, it is not a particularly good RF frequency reference. You cannot simply multiply a 1 Hz pulse into a clean 10 MHz signal with excellent phase noise.

The OCXO solves the opposite problem beautifully.

It produces a smooth, continuous signal with extremely low short-term noise. No real oscillator is perfectly pure. The signal is always wandering slightly in phase and timing, spreading a little energy outward from the ideal carrier into nearby frequencies. That spreading is what we call *phase noise*.

A good OCXO does this remarkably well. But as we have already seen, the OCXO slowly drifts.

The GPSDO combines the strengths of both systems through a very slow phase-locked loop.

Inside the unit, the OCXO output is divided down and compared against the incoming GPS 1 PPS signal. Any long-term phase difference between the two produces a tiny correction signal that gently nudges the oscillator back toward the GPS reference.

The important word here is *gently*.

The control loop operates very slowly, often over tens or even hundreds of seconds. Fast fluctuations in the GPS signal are mostly ignored. The OCXO is trusted to handle short-term stability on its own. The GPS reference only corrects the slower long-term drift.

In practice, the GPSDO becomes a negotiation between two very different notions of time.

The OCXO contributes short-term stability and low phase noise. GPS contributes long-term accuracy and traceability to UTC. One is locally quiet but slowly wandering. The other is globally accurate but noisy on very short timescales.

The discipline loop continuously balances the two.

The result is remarkably effective. The output becomes both stable and accurate in a way that neither contributor could achieve alone.

This is what makes modern GPS-disciplined oscillators so remarkable, especially at amateur-radio price points.

The DXPatrol GPSDO V3 uses a modern low-phase-noise synthesizer downstream of the disciplined reference to generate its output frequencies. The architecture allows arbitrary output frequencies with one millihertz resolution while maintaining very respectable spectral purity for amateur and laboratory use.

For most amateurs, this level of performance would have been almost unimaginable a few decades ago.

---

## Untangling the Vocabulary of Precision

At this point, we should probably pause and untangle a few words that amateurs often use interchangeably: accuracy, stability, phase noise, and jitter.

They are related ideas, but they are not the same thing.

**Accuracy** is about correctness. If an oscillator claims to produce exactly 10 MHz, accuracy describes how close it actually is to that value. Accuracy always depends on some external reference. By itself, an oscillator has no way to know whether it is truly correct. GPS discipline provides accuracy by tying the oscillator to atomic time standards.

**Stability** is different. Stability describes how consistently the oscillator behaves over time, regardless of whether it is perfectly accurate. A stable oscillator produces nearly the same frequency minute after minute and hour after hour, even if it happens to be slightly off frequency. The OCXO contributes this kind of stability. Once warmed up, it becomes extremely resistant to short-term wandering.

**Phase noise** describes something subtler.

No real oscillator produces a perfectly pure signal. Even a very good oscillator has tiny random fluctuations in phase and timing. In the frequency domain, those fluctuations spread energy outward from the ideal carrier into nearby frequencies.

That spreading is *phase noise*.

You can think of it as a kind of microscopic fuzziness around the carrier. A low phase-noise oscillator produces a clean, sharp signal. A noisy oscillator smears energy outward around itself.

This matters more than many amateurs realize. Close-in phase noise from a receiver’s local oscillator can make a strong nearby signal effectively raise the noise floor for weaker stations nearby. On a crowded band, phase noise often matters as much as raw sensitivity.

**Jitter** is closely related to phase noise, but viewed in the time domain instead of the frequency domain. Rather than asking how much energy spreads around the carrier, jitter asks how much the timing of the waveform wanders from its ideal position.

The DXPatrol unit specifies jitter below one picosecond RMS.

A picosecond is one trillionth of a second. Light travels only a fraction of a millimeter in that amount of time.

That is the level of timing precision sitting quietly on the bench in this little metal box.

Once you separate these ideas, a lot of confusion disappears.

An oscillator can be stable but inaccurate. It can be accurate but noisy. It can have excellent long-term frequency accuracy while still having mediocre short-term spectral purity.

A good GPSDO works because it balances these different qualities intelligently. The OCXO contributes short-term stability and low phase noise. GPS contributes long-term accuracy. The discipline loop continuously negotiates between them.

---

## What Does It Mean to Be Disciplined by the Sky?

We have traced the technical chain. Now it is worth stepping back and asking the larger question.

The word discipline turns out to be more interesting than it first appears. To discipline is not merely to correct. It is to bring something into alignment with a reference outside itself.

Left alone, the OCXO has its own sense of time. Precise. Self-consistent. But ultimately provincial.

Its “time” is the time of its crystal lattice, its thermal environment, its aging history. A local time, true to itself and to nothing else.

The GPS 1 PPS signal arrives from outside. Literally outside the shack and outside the atmosphere, from satellites orbiting roughly 20,000 kilometers overhead. And with it comes a shared definition of time. Not merely the output of one oscillator, but the consensus of atomic clocks, national standards laboratories, relativistic corrections, orbital mechanics, and international agreement about what “now” means.

The discipline loop becomes a conversation between the local and the global. The OCXO has its own sense of time: quiet, stable, and self-consistent, but ultimately local. Its “time” belongs to its crystal lattice, its temperature, and its aging history. The GPS reference arrives carrying a much larger frame of reference, and the oscillator slowly learns that its private sense of time is slightly wrong.

There is something quietly philosophical about this. The OCXO “knows” its frequency in the way a person knows their own heartbeat: intimately and reliably, but only from the inside. Left entirely to itself, the oscillator slowly drifts without realizing it. The correction has to come from outside, from a broader frame of reference that does not share the same local errors.

And somehow this entire chain now reaches the bench in an amateur radio shack. The reference on your desk traces back through satellites, atomic clocks, national standards laboratories, and ultimately to the definition of the second itself. Even that definition had to be corrected for relativity. A second on the surface of the Earth is not quite the same as a second in orbit. The clocks aboard the satellites are adjusted specifically because gravity and motion alter the rate at which time passes. Without those corrections, the system fails.

The oscillator sitting quietly on the bench is therefore being disciplined to a time reference that already includes corrections for the geometry of spacetime itself. Which is a rather astonishing thing to contemplate while sitting in the shack on a summer evening.

---

## The View From a Century

A century ago, amateur radio was still a frontier activity operating in what commercial interests dismissed as the “short wave” spectrum. Frequencies above roughly 1.5 MHz were widely considered unsuitable for serious long-distance communication.

The amateur community discovered otherwise.

Those early stations operated with frequency control that today would seem almost unimaginable. A crystal-controlled transmitter that stayed within a few hundred hertz was considered excellent. Variable-frequency oscillators drifted noticeably during warmup. Stability often meant waiting for the rig to thermally settle and learning the peculiar habits of your equipment well enough to compensate by feel.

As radio matured, frequency stability became increasingly important. Superheterodyne receivers made oscillator stability directly relevant to selectivity and tuning accuracy. Military development during the Second World War accelerated work on crystal control, temperature compensation, and precision frequency standards. After the war, amateurs benefited enormously from military surplus equipment and the engineering knowledge that accompanied it.

By the 1960s, atomic frequency standards existed, but they mostly lived in laboratories, observatories, and national standards institutions. Rubidium references, cesium beam standards, and hydrogen masers were remarkable instruments, but they were expensive, physically large, and well beyond the reach of most amateurs.

The idea that an amateur operator might someday own a frequency reference traceable to atomic time would have sounded almost absurd.

GPS changed that.

By the late 1990s and early 2000s, amateurs began building GPS-disciplined oscillators from surplus Motorola timing receivers and homebrew discipline circuits. What once required specialized knowledge, expensive surplus hardware, and considerable experimentation can now be purchased for around €180 in a small metal box with Wi-Fi connectivity and four simultaneous outputs.

That is a remarkable shift.

An amateur operator sitting in a small shack in rural Michigan, suburban São Paulo, or an apartment in Tokyo can now access frequency accuracy that, not very long ago, belonged almost exclusively to national standards laboratories.

And it is not merely a matter of lower cost, but something deeper, more profound.

A modern GPSDO connects the individual amateur to a global measurement infrastructure built from atomic clocks, satellites, relativity corrections, orbital mechanics, international coordination, and decades of engineering refinement. The timing reference arriving at the shack is part of a system operating at civilization scale.

And somehow all of that arrives through a little GPS antenna near the window and an SMA connector on the back of a small metal box sitting quietly on the bench.

One millihertz resolution. Sub-picosecond jitter. A few hundred dollars.

It is easy to become accustomed to numbers like these and forget what they actually represent. The scale of what is hidden inside this little device deserves to be appreciated.

---

## The DXPatrol GPSDO V3 as an Instrument

At some point, of course, we should probably talk about the device itself.

The DXPatrol GPSDO V3 is a thoughtfully designed little instrument. DXPatrol has managed to build something that feels both technically serious and very accessible to the amateur community.

The unit provides four independently configurable outputs, along with a front-panel 1 PPS reference output. In practical terms, that means a single small box can simultaneously provide a 10 MHz reference to a spectrum analyzer, a stable clock to an SDR, an injection frequency for a transverter, and precision timing to a computer or measurement setup.

That flexibility turns out to be genuinely useful in a modern shack.

The Wi-Fi configuration and app control sound slightly gimmicky at first, but in practice they are convenient. Setting frequencies from a phone or tablet is much easier than stepping through menus with a rotary encoder. The NTP server capability is also surprisingly useful. In a shack running digital modes like FT8 or WSPR, accurate computer time matters, sometimes more than people realize. The DXPatrol unit can quietly become the local time reference for the entire station.

The one millihertz frequency resolution initially sounds almost absurd, but it turns out to be practical in situations involving transverters, SDR calibration, or precision test equipment. And the phase-noise performance is genuinely respectable for a device in this price class. Independent measurements published by CT1DMK confirm that the unit behaves very much like a properly engineered GPSDO should.

The GPS antenna included with the unit is a standard active patch antenna on a three-meter cable. For many stations, placing it near a window is entirely adequate. More challenging installations may require a better sky view or a longer antenna run, but that is true of GPSDOs generally rather than a limitation specific to this unit. In my shack, it easily picked up several satellites with the antenna sitting on a windowsill.

Like all GPS-disciplined oscillators, the device ultimately depends on receiving satellite signals. Lose GPS coverage for long enough and the unit falls back to its internal oscillator, which remains very stable for some time but gradually loses long-term accuracy. In ordinary amateur use this is rarely a serious problem, but it is worth understanding.

The build quality feels appropriate for serious bench use. This is not a military or metrology-laboratory instrument with formal traceability certification and environmental hardening. But that is also part of what makes devices like this so interesting. Not very long ago, performance in this general class belonged almost entirely to laboratories, observatories, and government facilities.

For anyone working with SDRs, transverters, microwave systems, weak-signal digital modes, frequency measurement, or test equipment calibration, the DXPatrol GPSDO V3 is an easy device to recommend.

But even beyond its utility, it represents something larger.

It is a small, affordable interface to one of the most sophisticated timing infrastructures humanity has ever built.

---

## Epilogue: Time as Negotiated Reality

Augustine's ancient puzzle about time — that we know what it is until asked to explain it — has not been resolved by three millennia of philosophy and physics. What has been resolved, at least operationally, is how to *measure* it.

The measurement of time is always a negotiation between the local and the global, the immediate and the distributed, the physical and the conventional. The second is not a natural unit in the way that the speed of light is a natural constant; it is a human convention, defined with extraordinary precision through the physics of cesium atoms, maintained by international agreement, distributed through systems that correct for the curvature of spacetime.

Your GPSDO is a node in this global negotiation. Its OCXO is the local voice — stable, self-referential, proud of its thermal isolation and its short-term consistency. The GPS signal is the global voice — accurate, distributed, grounded in atomic physics and relativistic corrections, carrying the consensus of civilization about what time it is.

The discipline loop is the conversation between them.

A century ago, radio amateurs struggled to hold frequency within kilohertz. They warmed up their rigs, watched their dials, learned the signatures of their equipment's drift, compensated by hand. Frequency was something you negotiated with your apparatus, coaxed rather than commanded.

Today, for the cost of a few nights' dining, you can discipline your shack's time reference to atomic standards maintained in orbit, corrected for the relativistic effects of gravity and velocity, traceable to the international definition of the second. The drift is not coaxed away; it is continuously corrected by signals traveling at the speed of light from spacecraft that Einstein's physics made possible.

That is not merely technical progress. That is humanity's growing ability to agree, at ever finer resolution, about what time it actually is — and to make that agreement available to anyone with an SMA connector and a clear view of the sky.

The DXPatrol GPSDO V3 is a small, affordable, well-executed window into that agreement. It deserves a place in any serious shack — not merely for its utility, but for what it represents.

It represents the democratization of precision. And precision, properly understood, is not a technical specification. It is a relationship between the observer and the universe, negotiated at the edge of what physics allows.

---

*Written in the shack, late evening, while the GPS antenna watches the satellites pass.*

---

**Technical Specifications (DXPatrol GPSDO V3.2):**
- Output frequencies: 350 kHz – 350 MHz (LVCMOS), four independent outputs
- Frequency resolution: 1 millihertz
- Phase noise: < 0.7 ps RMS jitter
- Output phase adjustment: 0–360° (independent per channel)
- Reference: GPS-disciplined, 1PPS output
- Data output: NMEA via USB-C
- Control: Rotary encoder + Wi-Fi app (iOS/Android)
- Functions: NTP server, locator/UTC display, satellite count
- GPS antenna: Active patch, 3m cable, included
- Price: ~$250, available in the US via DXEngineering, or directly from DXPatrol, Portugal.

---

## Further Reading:

DXPatrol GPSDO V3  
- [DXPatrol Product Page:](https://dxpatrol.pt/produto/dxpatrol-gpsdo-v3/)
- [u-blox u-center GNSS evaluation software:](https://www.u-blox.com/en/product/u-center)
- [GPSDO V3 Meaurements by CT1DMK:](https://dxpatrol.pt/wp-content/uploads/2024/05/PN-GPSDO-V3-by-CT1DMK.pdf)

GPS and Timekeeping
- [GPS.gov — How GPS Works:](https://www.gps.gov/sites/default/files/2025-08/Educational_Poster.pdf)
- [NOAA - Globa Postioning Tutorial:](https://oceanservice.noaa.gov/education/tutorial_geodesy/geo01_intro.html)
- [Neil Ashby, Relativity in the Global Positioning System:](https://link.springer.com/article/10.12942/lrr-2003-1)
- [NIST: WWV and WWVH Time and Frequency Stations:](https://www.nist.gov/pml/time-and-frequency-division/time-distribution/radio-station-wwv)

Oscillators and Frequency Standards
- [Phase Noise and Frequency Stability:](https://rubiola.org/pdf-lectures/Scient-Instrum-Files/Phase%20noise%20Wiley%2C%20Ch2%20updated%20draft.pdf)
- ARRL Handbook sections on oscillators, PLLs, and frequency standards

---

