---
title: "Connecting Third-Party Drives to TwinCAT 3 Motion: Tips and Tricks"
date: 2025-10-26 12:00:00 +0000
categories: 
  - TwinCAT PLC Tips
tags:
  - TwinCAT
  - PLC
  - Motion
  - Tips
toc: true
---

In this post we’ll focus on connecting a third-party drive with TwinCAT 3 Motion using EtherCAT communication and the DS402 profile. We’ll cover how to add PDOs to Process Data and share an advanced trick to save time on non-standard drive linking.

## Introduction

TwinCAT automatically handles the linking of Beckhoff drives. If you're using AX series drives there's nothing to worry about. You may only run into problems when attempting to connect Beckhoff Motion to a third-party drive. But even for some third-party drives TwinCAT can automatically handle the linking on its own. For example the connection between Beckhoff Motion and Delta drives works exceptionally well.

Here are two rough videos showing my tests to control Delta ASDA-B3 drives using TwinCAT:

<iframe width="560" height="315" src="https://www.youtube.com/embed/GCXpx73AUXI?si=7EGQxFdm5j-TDhzC" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/jU9F2c51ujM?si=XH0Pliqw7_lurAwB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Basic linking

Recently Chris Chung the author of the blog http://soup01.com/en/ created a great tutorial on connecting TwinCAT with the Delta ASDA-A3. Below is the link:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ngLZH9JrsD4?si=LLH5oN379ub93b23" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

If you have a drive for which TwinCAT can perform the linking automatically I recommend checking out Chris's video. You'll find all the necessary information there.

We will focus on drives that require manual editing of the automatic linking. An example of such a drive is the Infranor Xtrapuls.

**Warning Notice:** Lorem ipsum dolor sit amet, consectetur adipiscing elit. [Integer nec odio](#). Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--warning}

**Danger Notice:** Lorem ipsum dolor sit amet, [consectetur adipiscing](#) elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum imperdiet.
{: .notice--danger}
