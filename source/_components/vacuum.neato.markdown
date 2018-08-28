---
layout: page
title: "Neato Robotics Vacuum"
description: "Instructions on how to integrate a Neato Botvac Connected Vacuum within Home Assistant."
date: 2017-10-18 16:11
sidebar: true
comments: false
sharing: true
footer: true
logo: neato.png
ha_category: Vacuum
ha_release: 0.57
ha_iot_class: "Cloud Polling"
redirect_from: /components/sensor.neato/
---

The `neato` vacuum platform allows you to control your [Neato Botvac Connected](https://www.neatorobotics.com/robot-vacuum/botvac-connected-series/).
The status will contain attributes on the robots last clean session.

To add `neato` vacuum to your installation, please follow instructions in [Neato component](/components/neato/).

Currently supported features are:

- `turn_on`
- `pause`
- `stop`
- `return_to_home`
- `turn_off` (stop all activity and return to dock)
