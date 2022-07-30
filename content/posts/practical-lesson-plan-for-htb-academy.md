---
title: "Practical Lesson Plan for HackTheBox Academy"
date: 2022-07-30T11:58:11-04:00
slug: 2022-07-30-practical-lesson-plan-for-htb-academy
type: posts
draft: false
categories:
  - education
tags:
  - hackthebox
  - htb academy
  - starting point
  - sense of pride and accomplishment
---

Over the last two months I've been focusing on improving my Red Team skills in
my spare time, as the security aspects of my day job fall well into the Blue Team camp.  For
this, I've been working through HackTheBox Academy classes (https://academy.hackthebox.com/)
and the Starting Point series on the main HackTheBox website
(https://app.hackthebox.com/starting-point).

I devised a plan to use them as complementary services:  try to complete all 21
machines of the Starting Point series, using HtB Academy instead of the
writeups. I worked through each machine using only the questions to guide me,
resorting to the writeup as a last resort.  When I needed to use the writeups,
I did not follow blindly along, instead I skimmed the writeup to figure
out what skill I was lacking, then I would take the associated HtB Academy course,
come back to the machine, and use what I learned to continue.

While this approach is definitely slower than following along with writeups or
YouTube videos, I learned far more than I would have from blindly copy-pasting
from a PDF, and it did give me a certain Sense of Pride and Accomplishment,
even if I was being guided by the questions.  "If I cannot create I cannot
understand" and all that.  (There are two exceptions to this rule of "don't rely
on the writeup" that I would recommmend, which I cover later.)

To aid anyone else that would like to be more proactive while doing Starting
Point, or just want some structure when doing HtB Academy classes, here I'm
providing the list of classes that I took in order, as well as improvements to
the lesson plan that I would make if I were doing it all over again.  Consider
this the missing syllabus for HackTheBox Academy 101.

# Time

All told, I completed 21 machines on the main HtB website and 22 classes
on HtB Academy.  HtB Academy has 51 classes in Tier 2 and below at the time
of this writing, putting this lesson plan at 43% of the content done.

This took me at least 8 hours a week (likely more) over the span of two months.
Hence my lack of posting for two months.  This also included a two-week span
where my wife was away on business and I reverted back to
bachelor-in-front-of-a-computer mode.  Being a real human being would add
another two weeks or so.

# Cost

If you want to follow this plan, you'll need to throw money at HtB eventually
to have access to the VIP machines on the main HtB website as well as cubes for
HtB Academy classes.

If you qualify for the Student plan and you're committed, that would be the
cheapest option.  While you only get access to Tier II and below classes,
this is not a major sacrifice as there's not many Tier III and IV classes,
and what classes exist tend to be highly specialized.  I'm also unsure whether
you keep access to modules you've completed after stopping your Student
subscription, however, this shouldn't be an issue if you're taking detailed
notes like you should be.

If you're not a student, one month of a Platinum subscription (68 USD for 1000
cubes) will be all you need to do the courses I've listed here, and four months
will give you enough cubes to buy all modules up to and including Tier III.

# Struggles

The one major stumbling block for me throughout Starting Point was Windows, as
my professional proficiency is in Linux environments.  It didn't help matters
that the Windows-specific content on HtB Academy are sluggish marathons
that tend to resemble reading textbooks and not the usual "gamified" material
that HtB strives for.

Accordingly, I found myself reaching for the writeup on Windows machines far
more than Linux machines, especially when it came to privilege escalation.
However, had I not forced myself to complete the Starting Point series, I
probably would have stuck to Linux boxes and avoiding Windows boxes entirely,
so it was worth it to allow myself to cheat here to expand my skillset.

# The Class List

## Starting Point Tier 0

This is a lightweight tier, where you're learning how to use individual
services.  Not much exploitation going on, unless you're a politician who
considers downloading a file from a public share to be "hacking".  There's a
good chance that you could finish this Tier without doing any of the HtB
Academy courses, just by following the hand-holding questions.

That being said, I came into this Tier having already done the following
classes:

* Introduction to Academy
* Linux Fundamentals
* Introduction to Networking
* Web Requests
* JavaScript Deobfuscation
* Getting Started

Out of all these classes, "JavaScript Deobfuscation" could be dropped if you're
really tight on time. as it's not a skill that's used in this series.  (The
only time I can remember using it is in the Skill Assessment for Server-Side
Attacks.)

If I were to change anything, I would add  "Windows Fundamentals" to this Tier,
perhaps right after "Linux Fundamentals".

## Starting Point Tier 1

Starting Point Tier 1 is where we start doing actual exploitations;  however,
there's not much in the way of pivoting or exploitation chaining going on.
This is probably the longest Tier in terms of classes, as we'll be learning how
to do various exploits by hand:

* Network Enumeration with Nmap
* Introduction to Web Applications
* SQL Injection Fundamentals
* File Inclusion
* Attacking Web Applications with Ffuf
* Login Brute Forcing
* Using Web Proxies
* Cross-Site Scripting (XSS)
* Server-Side Attacks

If I were to change anything here, I would move "Attacking Web Applications
with Ffuf" and "Using Web Proxies" much earlier, right after the Nmap course,
and also add "Intro to Network Traffic Analysis" to this Tier.

## Starting Point Tier 2

Starting Point Tier 2 is where we start chaining exploitations and engage in
pivoting; accordingly, privilege escalation is the name of the game here.  This
is likely the Tier where you'll need to "cheat" and look at the writeups
from time to time, especially if you're not a Windows expert:

* Windows Fundamentals
* Introduction to Active Directory
* Linux Privilege Escalation
* SQLMap Essentials
* Intro to Network Traffic Analysis
* Introduction to Bash Scripting
* Web Attacks

As I previously mentioned, I would move "Windows Fundamentals" and "Into
to Network Traffic Analysis" into earlier Tiers; if I were going to add anything
new, it would be "Windows Privilege Escalation".

As an aside, the "Unified" machine is a special case where I'd recommend following
along with the writeup because it contains two specific exploitations (the Log4J
vulnerability and NoSQL databases [specifically MongoDB]) that do not appear to
covered by any HtB Academy course.

## Additional Courses 

Here's a list of classes that I did not take to complete Starting Point, but
could be useful:

* Windows Privilege Escalation:  This is the big one I've omitted;  if you have
  enough time or Windows is a necessary skill for you, this is absolutely a
  class you should take.
* Cracking Passwords with Hashcat:  The Starting Point machines use John the
  Ripper for cracking passwords, not Hashcat, but the principles are the same.
  If concepts like hashes, dictionary attacks, and rainbow tables are unknown
  to you, it's probably a good idea to take this course.
* File Transfers:  This is a topic that enough of the other courses cover
  (the Getting Started module has a section on this, for example) that you'll
  know the basics through osmosis.  Supposedly has some info on evading
  detection, which could be useful, but this doesn't show up in the Starting
  Point machines.
