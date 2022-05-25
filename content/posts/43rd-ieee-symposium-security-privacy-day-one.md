---
title: "43rd IEEE Symposium on Security and Privacy, Day One"
date: 2022-05-25T17:43:02-04:00
slug: 2022-05-25-43rd-ieee-symposium-security-privacy-day-one
type: posts
draft: false
categories:
  - conferences
tags:
  - 43rd ieee symposium on security and privacy
  - iot
  - vr
  - authentication
---

Attended the first day of the 43rd IEEE Symposium on Security and Privacy ([website](https://www.ieee-security.org/TC/SP2022/))
for my day job... by which I mean I finally got around to watching the recordings for
the first day, two days later.  Virtual conferences are a wonderful thing.
Figured I'd write about it here, partially because it's relevant, and partially
because I'm expecting a bean counter at my day job six months from now to order me
to prove I really did "virtually attend" it.

Decent conference, academics speaking to academics.  Reminded me of my past life
as a physicist.  Not going to lie, every time I saw a mathematical formula that
someone had clearly copy-paste'd from a LaTeX document, I felt a little nostaglic
for my postdoc glory days of working 80 hour weeks making less than a fresh college grad.
Nothing on the first day was relevant for my day job, so I went with the Smart
Home and Virtual Reality session, because I'm not enough of a paranoid lunatic
already.  The session was short (only three talks), might as well describe them
all:

First talk was "SoK:  Authentication in Augmented and Virtual Reality" by Stephenson et al.  As the
title suggests, it was a review-article-esque talk about existing methods in
practice and literature for authentication from within an AR/VR environment.
Some should be pretty familiar to anyone that's used a VR headset before:  use
a virtual keyboard within VR to enter your password, log into a linked device on
your network.  My personal favorite was an "obfuscated PIN" approach, which is a
PIN-based approach with the added twist that the user is shown a numeric keypad
with a one-time pad applied on top of it within the VR/AR environment.  The user
then speaks their PIN out loud encoded by the one-time pad.  Clever exploitation
of the fact that we memorize PINs spatially and not numerically.  The authors
were touting biometrics especially; I personally don't want to worry about my
iris scans being leaked, and I suspect I'm not alone.

Next talk was "Delay Wreaks Havoc on Your Smart Home:  Delay-based Automation
Interference Attacks" by Chi et al.  Was about phantom-delay attacks in IoT, which is a
man-in-the-middle attack where the MitM delays IoT messages back
to the servers to mess with the ordering and consistency of messages.  The
authors proposed a "delay-based automation attack interference attack" where
an attacker can delay triggers for home automation rules to carry out attacks:
a "lock the front door when I'm away" rule will leave the front door
wide open for thieves if an attacker can delay the "I'm away" message back to
the server, and "sound the alarm at night if I'm not moving but there's movement
in the house" can be circumvented if the "I'm not moving" message is delayed.
Several well-known home automation systems are vulnerable, so not a strictly
academic concern. 

The final talk of the session was "Peekaboo: A Hub-Based Approach to Enable
Transparency in Data Processing within Smart Homes" by Jin et al., where the authors
propose a framework spawned out of talks with Google Nest that proveably collects only aggregate data from edge devices
"to assure users" (more on that later).  Functionally, it's a programming paradigm
where preprocessing operators can be connected to data sources to allow
developers to control how fine- or coarse-grained data is collected, and this is
the only way for developers to access data sources (white-list-only).  Think of
having a "weekly" preprocessing operator which connects to a "screen on" data
stream to generate the "weekly screen usage" report that Android and iPhone
provide.

Part of me feels bad for what I'm about to say, because the presenter was just
a kid trying to get his PhD (the moderator said as much in her introduction),
but this approach is misguided for the reason that the presenter himself
brought up early on in his talk, when he argued against open sourcing "because
reading source code is too much work" (what?):  the IoT device is still a black
box.  In particular, it is a black box controlled by a "big tech" company
which is itself collecting and storing absurd amounts of data.  Adding
aggregation methods doesn't change this;  to aggregate data over various time
periods, I need a data stream precise enough to feed all those aggregation
methods in the first place.

People aren't mistrustful of apps running on smart devices, they're mistrustful of the smart device itself.
Your average user isn't shying away from buying an Alexa device because they're afraid of the developer of an Alexa skill stealing
data, they're afraid of Amazon.  They don't care whether the microphone is passing
data to an app in a fine- or coarse-grained fashion, they're concerned that the
microphone exists at all.  If anything, users of IoT devices *want* ridiculously
fine grained data from their IoT device, they *want* their Apple Watch to tell
them exactly what their heart rate was to the minute five days ago or their
performance on their Peloton ride from three months ago to the second.  The
problem isn't the degree of aggregation, the problem is trust in the data provider.
There's a reason I mentioned the Google Nest connection.  I can't help
shake the feeling that Google Nest's motivation is to attempt to solve a "problem"
that the industry has amplified to try to distract the average consumer
("see, we're safe, we're AGGREGATING your data!")  This may have worked ten years
ago, but consumers have become jaded and cynical, and rightly so.

Peekaboo has legitimacy, don't get me wrong, and the problem it solves is a valid
one.  Hope the kid gets his PhD.

That's it for this installment of "Hurricane Shark takes too detailed of notes
to avoid packing for yet another trip", posts for next two conference days
hopefully won't be this rambling.
