---
title: "Reproducible Research Papers"
weight: 5
aliases: []
tags: ["reproduciblility", "research", "publications", "science"]
categories: ["workshops"]
showToc: true
TocOpen: true
hidemeta: false  # "suggest changes"
description: "Making Your Research Reproducible with LaTeX and Containerization"
cover:
    image: "" # image path/url
    alt: "<alt text>" # alt text
    caption: "<caption text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
---

## Overview
In this workshop, we'll be covering how to make your entire paper (figures and all) reproducible. The goal is that anyone who wants to be able to take your raw data and reproduce all of the plots (and underlying statistical analyses being visualized) with the ease of issuing one command / clicking a single button in a web browser.

Reproducibility is a critical aspect to consider when conducting and sharing research. Not only does it strengthen the validity and credibility of findings, but it also facilitates revisiting and building upon work in the future.

It's worth noting that reproducibility encompasses not just sharing code, but also ensuring the transparency and trustworthiness of methods and results. Adhering to best practices in reproducibility can enhance the reputation of researchers and bolster trust in their work.

## Motivations

### Why Care About Reproducibility?

Reproducibility is critical for scientific credibility and the validity of research findings. When your work can be easily reproduced by others, it increases the trust and confidence in your results. Moreover, reproducibility is important for your own benefit as well. You never know when you'll want to revisit your work in the future, or when you'll need to build on it. When your work is easily reproducible, it will be much easier for you to pick up where you left off. 

### Benefits for Your Future Self

Research can be a challenging and time-consuming process, and one frustration researchers often encounter is not being able to easily find or recall the methods and data used to produce their results. By making your work reproducible, you can avoid this frustration and ensure a smooth experience when revisiting your work in the future.

Having a clear, concise, and easily accessible record of your methodology and data will save you time and effort. You won't have to waste precious time retracing your steps or trying to figure out how you arrived at your results. This means that you can spend more time building upon your existing work and making new discoveries, rather than being bogged down by the tedious task of reconstructing your research.

By adopting best practices in reproducibility, you'll also benefit your future self by fostering a sense of organization and structure in your research. This will make it easier for you to collaborate with others, share your work, and publish your findings, leading to a more impactful and successful research career.

In short, making your work reproducible will benefit both your current and future self, allowing you to focus on what truly matters - conducting groundbreaking research.

### Approaches to Reproducibility

Even a simple, yet messy, approach to reproducibility is better than having no approach at all. As experience grows, participants may find that a structured approach to code that promotes flexibility and adaptability is even more advantageous, as it can facilitate collaboration and contribution from others, amplifying the impact of the work.

In this workshop, various approaches to reproducibility will be covered, from straightforward scripts to more structured and abstracted libraries and packages. The objective is to equip participants with the necessary information to make informed decisions about the best way to reproduce their research and to support them in making their work more accessible and impactful.

> The workshop will provide participants with the tools and knowledge to make their research reproducible, including LaTeX documents and analysis code, allowing for easy verification and building upon by others.


## Presentation Structure

1. Introduction: In this module, we'll discuss the motivations for making research reproducible, including how your "future self" will benefit, the importance of scientific credibility, and how reproducibility can save time.

2. Reproducing the PDF itself (going from images and LaTeX code to a publication-ready paper for submission to arxiv.org), complete with bibliography. Here we'll cover what is involved with LaTeX reproducibility, and talk about tools like `latexmake` for automating the compilation, with the outcome of providing a docker container capable of taking the source code of the paper in the repo and producing a PDF.

3. Reproduction of the analyses and figures in the paper. This is about how we provide a reproducible compute environment (enabled by containerization technology, which we'll overview in this section) capable of taking raw data and outputting all of the figures/tables required for inclusion in the final paper.


## Learning Outcomes

By the end of this workshop, participants will learn how to:
- Use LaTeX to produce professional-grade research papers, including formatting and bibliography.
- Automate the process of compiling their paper using tools like `latexmake` and leverage `Makefile` for describing dependencies in analyses.
- Think about how someone else will reproduce all the figures and tables in their paper from raw data.
- Create reproducible compute environments using containerization technology such as `docker` and share them (e.g., mybinder.org).
- Understand the importance of reproducibility in research, and the benefits of making their work easy to reproduce.

## Workshop Format

1. Presentation: 90 minutes covering the lesson plan above
2. Application: An optional 3-8 hour "office hours" style hands-on component where participants can practice what they've learned and receive help with reproducing their own research. This section is limited to members of the same research groups/labs to tailor solutions to specific needs.

See the [workshop structure](/workshops/info) page for more information about general workshop format.