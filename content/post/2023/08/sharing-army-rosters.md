---
title: Sharing army rosters
author: matt40k
type: post
date: 2023-08-13T00:00:01+00:00
url: /2023/08/sharing-army-rosters/
type: post
description: 'An idea for how to share army rosters'
draft: false
tags: 
  - 40k
categories:
  - 40k
---
When having a game of Warhammer 40,000, you build your army list and you're suppose to share your army list with your opponent before battle commences. The idea is to provide transparency in what units you are using. Games Workshop provides templates that can be used that can be downloaded for free from [Warhammer Community](https://www.warhammer-community.com/wp-content/uploads/2023/06/idTDLhettxA8bXeg.pdf).


One of the problems with doing this is WHEN. If you share just before you start the battle, if you, or your opponent is unaware of the opponents army, its the equalivate of sharing nonsense. They won't know what each models does, what its strengths and weakness are, if you are lucky, they will explain a basic overview. If you are unlucky they will decide what list they share based on what your list detailed. Horror stories such this one on Reddit occurs

> We had a player at our club who was pretty bad for that. We’d arrange a game in the group chat a few days before and then he’d arrive with a list that coincidentally had exactly the right units to hurt your army. We started telling him we were bringing one army then “changing our mind” and bringing something different on the day.
>
> He used to be even worse, he’d “forget” to write a list then do it on the spot while you unpacked your army. One of our guard players got sick of this one night. He began to unpack his army out of its cases, he put several leman russes and chimeras on the table, let the other player write his list full of AT weapons, the pushed the tanks aside and got out 300 conscripts.
>
> Source: [siremilcrane](https://www.reddit.com/user/siremilcrane/) via [reddit](https://www.reddit.com/r/WarhammerCompetitive/comments/zlmpba/do_you_normally_share_your_army_list_in_advance/j06p05s/)

So, how do you get around this? With an army roster sharing service.

These are just my notes on how an army roster sharing service might work.

Ideally, it would work with Games Workshop authenticiation - Sign in to My Warhammer.

You should be able to share from the official Warhammer 40k app - either export as text then pop it into the army roster sharing service.

It should provide some sort of validation - that the army is correct, its not over points or breaking limits.

It should be able to be printed - export as PDF.

The printed version, such as PDF, should include a QR coded URL to the army roster.

The url should default to the web version, however changing the extension to json or pdf should render in the relevate format.

It should be able to be analysed, there should be stored in a machine readable format - json for example. This could provide analysis on army lists being generated and how changes affect historic army lists.

Data could be sorted in json format on object storage, such as s3.

Files could then be restricted to be viewable after a data using conditional ACLs. This means the end user could submit an army list, then set a "viewable" date. This would allow them to share url to the army list with their opponent, however they wouldn't be able to view the actual list until that date when it unlocks. This deals with the who goes first problem.

Future enhancements could be to include integration with Games Workshop Trade so it could allow booking tables with Games Workshop stores or independant retailers.