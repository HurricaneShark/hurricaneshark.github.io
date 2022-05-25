---
title: "Adding Plausible Analytics to Website"
date: 2022-05-25T15:34:22-04:00
slug: 2022-05-25-adding-plausible-analytics
type: posts
draft: false
categories:
  - website
tags:
  - plausible
  - analytics
  - matomo
  - hugo
  - privacy
  - gdpr
---

Added Plausible Analytics ([plausible.io](https://plausible.io)) to the website
last night.  Debated if I should make a post about it, figured that I might as
well in case anyone accuses me of having "secret" trackers in the future.

Out of all the options I looked into, Plausible and Matomo were the two strongest
privacy-focused trackers that offered both free roll-your-own (if I ever choose
to go the self-hosted route again) and paid cloud versions.  Plausible ultimately
won out because its tracking script is tiny and Matomo upcharges for features in
its self-hosted option.  Cloud-hosted Plausible has no free option, but honestly
that helps me trust it more, not less.  Free web services cost too much.

Installing Plausible Analytics in Hugo was pretty simple:  figure out which file
in your theme contains the template to generate the `<head>` block, create a
copy of that file in the base `layout` folder (including subfolders if needed)
to overwrite the default template during site generation, and copy a tiny script
Plausible provides into the `<head>` block template in the copied file.  Done.
In the Hugo theme I'm currently using (smol), the `<head>` block was not located
in any file in `layouts/partials/` as most online documentation including Hugo's
official documentation suggests, but rather in `layouts/_default/baseof.html`.
Something to keep in mind.

There's an option to open up the analytics to everyone.  I commend them for the
idea, but think it's too much of a security risk on *my* end, i.e. could be used
by an attacker to geolocate me.  Good idea for privacy-minded companies with
public mailing address in their footers, bad idea for individuals.

Plausible also has the nice perk that it's engineered to be cookie-less and
satisfy GDPR with no required, ugly pop-up that is rendered functionally
pointless by everyone's muscle memory being trained to click through it anyway,
but that's a topic for another post.
