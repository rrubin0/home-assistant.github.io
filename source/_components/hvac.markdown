---
layout: page
title: "HVAC"
description: "Instructions on how to integrate HVAC devices status with Home Assistant."
date: 2016-05-07 09:00
sidebar: true
comments: false
sharing: true
footer: true
ha_release: 0.19
---

<p class='note warning'>
**This component has been deprecated in favor of the "[climate](/components/climate/)" component and will be removed in the future. Please use climate.**
</p>

The `hvac` component is built for the controlling and monitoring of HVAC (heating, ventilating, and air conditioning) devices.
 
To enable this component, pick one of the platforms and add it to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
hvac:
  platform: demo
```

