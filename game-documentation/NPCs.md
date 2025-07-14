---
title: NPCs
description: 
published: true
date: 2025-07-14T20:35:38.356Z
tags: 
editor: markdown
dateCreated: 2024-12-11T03:15:43.217Z
---

# NPCs

**NPCs (non-player character)s** in SCP Architect X serve many functions for your foundation.

**NPCs are meant to be predictable, and have limited random properties or decisions unless explicitly stated**.

## Current NPCs

This is a list of current NPCs within the game, their function, and cost to hire.

|     |     |     |
| --- | --- | --- |
| **NPC Name** | **Function** | **Cost** |
| Scientist | Performs tests using test subjects. | $1000+ |
| Security | Required for testing Euclid humanoid SCPs. | $1500+ |
| Test Subject | Required for tests to occur. Automatically hired when old bed is placed. | Free |

## NPC Metrics

NPCs have 3 major metrics, **Bathroom, Hunger, & Energy.**

|     |     |
| --- | --- |
| **Metric** | **Description** |
| Bathroom | The bathroom metric shows the accessibility and use of toilets for NPCs.   <br>To increase this metric, you should place more toilets across your facility. |
| Hunger | The hunger metric shows the accessibility and use of cafeteria tables for NPCs.  <br>To increase this metric, you should place and link more cafeterias across your facility. |
| Energy | The energy metric shows the amount of rest and use of beds for NPCs.  <br>To increase this metric, ensure all staff and test subjects have a sufficient amount of beds. |

You view your overall NPC metrics by visiting the [Foundation Management](https://wikix.scparchitect.com/en/game-documentation/foundation-management) tab.

## NPC Prices

The cost of hiring scientists and security grows exponentially as you hire. 

1.  The base cost for scientists is **$1000**
2.  The base cost for security is **$1500**

### Math

The prices for NPC's are determined by this

f(c,n)=round(c⋅1.4n)f(c, n) = \\mathrm{round}(c \\cdot 1.4^n) f(c,n)=round(c⋅1.4n)

where

ccc - base cost (1000 for Scientist and 1500 for security)

nnn - number of NPCs (of whichever type you're buying) that you already have

In this provided function, it's raising 1.4 (the scaling factor / growth rate) to the nnn and then multiplying it by ccc followed by rounding it to a whole number

Think of ccc as the base cost,  
and 1.4n1.4^n1.4n as the inflation multiplier that increases the price each time you buy another one.

The total cost of buying nnn NPCs:

total(c,n)=round(c⋅1.4n−11.4−1)\\text{total}(c, n) = \\mathrm{round}\\left(c \\cdot \\frac{1.4^n - 1}{1.4 - 1}\\right) total(c,n)=round(c⋅1.4−11.4n−1​)

# NPC Behavior

Outlined below is the static behavior of every NPC. An NPC's lifecycle is a loop of actions and decisions an NPC will make during it's life time (from hiring to firing).

// for braden to do when behavior trees are implemented