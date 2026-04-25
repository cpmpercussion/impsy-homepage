---
layout: page
title: Research
subtitle: Publications, history, and the ideas behind IMPSY.
permalink: /research/
description: Publications and research history of the IMPSY (Intelligent Musical Prediction System) project, from the early Robojam MDRNN work through to the 2026 design-space paper.
---

IMPSY sits in a research thread that began with mixture density recurrent networks for musical interaction and has grown into a general toolkit for intelligent instruments. The papers below describe the system, the ideas, and the user studies that have shaped it.

## Publications

<ul class="pub-list">
  <li>
    <div class="pub-year">2026</div>
    <div class="pub-title">Opening the Design Space of Intelligent Musical Instruments with IMPSYpi</div>
    <p class="mb-2 text-body-secondary">The most recent paper. Documents the IMPSYpi distribution, surveys instruments built with the system, and frames a design space for embedded intelligent musical instruments.</p>
    <a href="https://github.com/cpmpercussion/impsypi-opening-design-space-paper">Paper repository →</a>
  </li>
  <li>
    <div class="pub-year">2020</div>
    <div class="pub-title">Understanding Musical Predictions with EMPI</div>
    <p class="mb-2 text-body-secondary">A study of embodied musical prediction using the EMPI hardware controller. Examines how performers experience, interpret, and play with predictive output from an MDRNN.</p>
    <a href="https://github.com/cpmpercussion/Understanding-Musical-Predictions-with-EMPI">Paper repository →</a>
  </li>
  <li>
    <div class="pub-year">2019</div>
    <div class="pub-title">An Interactive Musical Prediction System with Mixture Density Recurrent Neural Networks</div>
    <p class="mb-2 text-body-secondary">The original IMPS paper. Introduces the prediction system, focuses on OSC connectivity, and lays out the machine learning approach that later became IMPSY.</p>
  </li>
  <li>
    <div class="pub-year">2018</div>
    <div class="pub-title">RoboJam: A Musical Mixture Density Network for Collaborative Touchscreen Interaction</div>
    <p class="mb-2 text-body-secondary">An earlier collaborative-performance system that established the MDRNN principle on which IMPS / IMPSY were later built.</p>
    <a href="https://github.com/cpmpercussion/robojam-an-interactive-musical-mdn">Paper repository →</a>
  </li>
</ul>

## Project timeline

<ul class="timeline">
  <li><span class="year">2017–18</span> Started the musical MDRNN idea with the Robojam project — collaborative touchscreen performance driven by a mixture density network.</li>
  <li><span class="year">2019</span> Released IMPS, generalising the MDRNN approach to arbitrary musical interaction over OSC.</li>
  <li><span class="year">2020</span> Studied IMPS in performance with the EMPI embodied controller; published findings on predictive interaction.</li>
  <li><span class="year">2024</span> Rebuilt IMPS as <strong>IMPSY</strong> with broader I/O, easier configuration, and a focus on Raspberry Pi deployment for new intelligent instruments.</li>
  <li><span class="year">2024</span> Presented IMPSYpi at <a href="https://github.com/smcclab/nime-embedded-ai">NIME 2024 (Embedded AI workshop)</a>.</li>
  <li><span class="year">2026</span> Updated IMPSY for a modern install path, clarified the web interface, and started connections with the <a href="{{ site.links.mishmash }}">Mishmash</a> project.</li>
</ul>

## Wider context

The IMPSY project is developed at the [Sound, Music, & Creative Computing Lab]({{ site.links.smcclab }}) by [Charles Martin]({{ site.links.charles }}) and collaborators. For ongoing news, talks, and related work, those sites are the best place to look — there is intentionally no blog or news feed here.
