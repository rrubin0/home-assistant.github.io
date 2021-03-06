---
layout: page
title: "Roku"
description: "Instructions how to integrate Roku into Home Assistant."
date: 2016-05-16 20:0+0000
sidebar: true
comments: false
sharing: true
footer: true
logo: roku.png
ha_category: Media Player
ha_release: "0.20"
---

The [Roku](http://www.roku.com/) media players will be automatically discovered if you enable the [discovery component](/components/discovery/).

The `roku` media player platform can also be forced to load by adding the following lines to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
media_player:
  platform: roku
  host: 192.168.1.10
```

Configuration variables:

- **host** *Optional*: Use only if you don't want to scan for devices.
