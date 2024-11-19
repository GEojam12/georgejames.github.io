---
title: "R tip of the day"
subtitle: "GGtheme"
author: "George James"
date: "November 7, 2024"
format:
  revealjs: 
    slide-number: true
    preview-links: auto
    self-contained: true
editor_options: 
  chunk_output_type: console
---

## {auto-animate=true}

::: {style="margin-top: 200px; font-size: 2.5em; color: blue;"}
An intro to ggthemeassist
:::

## GGThemeAssist function in R


-This package works as an add in in R studio


-This package in R allows us to go more into depth in Data visulization. Instead of just adding a color of a clean_theme. 


-This package is very useful for people who don't want to code every detail of the ggplot. Especally the changes that are less obvious. 

```{r}
library(tidyverse)
library(ggplot2)
library(ggThemeAssist)
library(palmerpenguins)
```






## before ggtheme {auto-animate=true}

``` {.r}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g)
) +
  geom_point()
```

```  {r}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g)
) +
  geom_point()
```

## plot results
```{r}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g)
) +
  geom_point() + theme(plot.subtitle = element_text(family = "mono",
    size = 8, face = "italic"), axis.line = element_line(linetype = "twodash"),
    panel.grid.major = element_line(linetype = "blank"),
    panel.grid.minor = element_line(linetype = "blank"),
    axis.title = element_text(family = "mono"),
    axis.text = element_text(size = 9), axis.text.y = element_text(size = 8),
    plot.title = element_text(family = "mono"),
    panel.background = element_rect(fill = "white"),
    plot.background = element_rect(fill = "azure",
        colour = NA)) +labs(title = "Happy Feet", x = "Flipper Length(mm)",
    y = "Body Mass(g)", subtitle = "Flipper length and body mass of penguins")
```

## After ggtheme {auto-animate="true"}

``` {.r code-line-numbers="4-15"}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g)
) +
  geom_point() + theme(plot.subtitle = element_text(family = "mono",
    size = 8, face = "italic"), axis.line = element_line(linetype = "twodash"),
    panel.grid.major = element_line(linetype = "blank"),
    panel.grid.minor = element_line(linetype = "blank"),
    axis.title = element_text(family = "mono"),
    axis.text = element_text(size = 9), axis.text.y = element_text(size = 8),
    plot.title = element_text(family = "mono"),
    panel.background = element_rect(fill = "white"),
    plot.background = element_rect(fill = "azure",
        colour = NA)) +labs(title = "Happy Feet", x = "Flipper Length(mm)",
    y = "Body Mass(g)", subtitle = "Flipper length and body mass of penguins")
```

## lets see another example and a walk through: {auto-animate="true"}

```{r}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g, color = species)
) +
  geom_point() + theme(panel.grid.major = element_line(linetype = "blank"),
    panel.grid.minor = element_line(linetype = "blank"),
    panel.background = element_rect(fill = "gray97"))
```

##  ggtheme:{auto-animate="true"}
```{r}
ggplot(
  data = penguins,
  mapping = aes(x = flipper_length_mm, y = body_mass_g, color = species)
) +
  geom_point() + theme(panel.grid.major = element_line(linetype = "blank"),
    panel.grid.minor = element_line(linetype = "blank"),
    plot.title = element_text(size = 15,
        face = "bold", hjust = 0.5, vjust = 1),
    panel.background = element_rect(fill = "gray97")) +labs(title = "Species and Size", x = "Flipper Length(mm)",
    y = "Body Mass(g)", colour = "Species")
```
