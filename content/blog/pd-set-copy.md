---
title: "About the Pandas SettingWithCopyWarning"
date: 2022-08-30T11:30:03+00:00
# weight: 1
aliases: ["pandas-warning"]
tags: ["pandas"]
categories: ["resources"]
showToc: false
TocOpen: false
draft: false
math: true
hidemeta: false
comments: false
description: "How to fix an annoying warning."
summary: "How to fix an annoying warning."
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: false
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<image caption>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: false # only hide on current single page
---


## tl;dr
Turn the `SettingWithCopyWarning` into an explicit error that you are forced to fix by setting

```python
import pandas as pd
pd.set_option("mode.chained_assignment", "raise")
```

## Problem
`pandas` is complaining to you with the following warning (which only shows up on first execution):

```
SettingWithCopyWarning: A value is trying to be set on a copy of a slice from a DataFrame.
```

## Solution

Use `pd.set_option("mode.chained_assignment", "raise")` to force yourself to actually fix the underlying piece of offending code.

Most often you will need to explicitly call `.copy()` on a sub-dataframe you want to manipulate, particularly when you want to ensure that changes you make to the "slice" of the DataFrame do not propagate back to the original object.
Credit to [this article][tds] for explaining the problem and solution.

[tds]: https://towardsdatasceince.com/settingwithcopywarning-in-pandas-782e4aa54ff7#0e7a
