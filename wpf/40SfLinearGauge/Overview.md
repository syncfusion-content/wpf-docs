---
layout: post
title: Overview
description: overview
platform: wpf
control: Linear Gauge 
documentation: ug
---

# Overview

## Introduction

The Linear Gauge displays a range of values graphically along the linear scale. It can very well be designated as the linear form of the Circular Gauge. It measures the values of the scales and can be presented in the horizontal or vertical sliding or meter.

Use Cases

These are used in the,

1. Thermometer.
2. Real world applications such as volume control.
3. Industries to visualize the pressure and temperature and many more.
4. Sensors like equipment.
5. Visualization of memory usage.
## Key features


The Linear Gauge is a highly customizable control with more APIs to modify the look and feel of the control without any hurdles of the editing template. The customizable elements of the Bullet Graph such as Ranges, Ticks, Labels, and Pointers are easy to use.

A Linear Gauge contains the MainScale that is the central UI component. You can see a Linear Gauge in the Visual Studio Designer while you click and drag the Linear Gauge icon from the ToolBox. The view of the Linear Gauge can be changed by setting the Orientation of the Linear Gauge. The MainScale is a linear scale that comprises the following components:

1. Ticks
2. Labels
3. Ranges
4. Pointers

Ticks

Linear Gauge scales are designed with the following two kinds of ticks: 

5. Major Ticks are the primary scale indicators.
6. Minor Ticks are the secondary scale indicators that falls between the major ticks.

Labels

Labels are quantified to specify the numeric values for major ticks based on the interval of the linear scale.

Ranges

Linear scale can contain one or more ranges. A range shows the start and end values of the inner divisions within the linear scale’s whole range. Each range could show different zones or regions of the same metrics: like high, low, and average temperature range.  

Pointers

Pointer is a key element of the linear scale that points a value or measure on that scale. A linear scale can have one or more pointers that can be used to measure different values for different criteria. Each pointer has a Value property that specifies the current value of the linear scale based on its measurement.

## Linear Gauge Elements

{ ![](Overview_images/Overview_img1.jpeg) | markdownify }
{:.image }


