---
layout: page
title: "Google Assistant via Home Assistant Cloud"
description: "Enable the Google Assistant via Home Assistant Cloud integration."
date: 2017-11-17 20:00
sidebar: true
comments: false
sharing: true
footer: true
---

<p class='note'>
The minimum supported version of Home Assistant is 0.65.6.
</p>

The Google Assistant integration allows users to control the entities via the Home Assistant Smart Home skill for Google Assistant. This means that you can say things like "Ok Google, turn on the kitchen light" to control your local Home Assistant.

To use this integration, you need to have:

 - The cloud component set up. [Learn more](/components/cloud/)
 - A Google Assistant enabled device like the Google Home or a mobile phone running Google Assistant.
 - Activated the Home Assistant Smart Home skill for Google Assistant.
   - If you have a Google Home device, use the Google Home app, select *Home control*, and then add *hass.io* using the *Add devices* option.
   - If you only have a mobile phone, launch Google Assistant, select the three dots menu. Under *Settings* you'll find *Home Control*. There you can add *hass.io* using the *Add devices* option.

You can use `configuration.yaml` to configure the entities that are being shown to Google Assistant and how they are exposed.

```yaml
# Example configuration.yaml entry configuring Google Assistant
cloud:
  google_actions:
    filter:
      include_entities:
        - light.kitchen
        - light.kitchen_left
      include_domains:
        - switch
      exclude_entities:
        - switch.outside
    entity_config:
      switch.kitchen:
        name: Custom Name for Google Assistant
        aliases:
         - bright lights
         - entry lights
        room: living room
```

{% configuration cloud %}
google_actions:
  description: Configuration options for the Google Assistant integration.
  required: false
  type: map
  keys:
    filter:
      description: Filters for entities to include/exclude from Google Assistant.
      required: false
      type: map
      keys:
        include_entities:
          description: Entity IDs to include.
          required: false
          type: list
        include_domains:
          description: Domains to include.
          required: false
          type: list
        exclude_entities:
          description: Entity IDs to exclude.
          required: false
          type: list
        exclude_domains:
          description: Domains to exclude.
          required: false
          type: list
    entity_config:
      description: Entity specific configuration for Google Assistant.
      required: false
      type: map
      keys:
        '`<ENTITY_ID>`':
          description: Entity to configure
          required: false
          type: map
          keys:
            name:
              description: Name of entity to show in Google Assistant.
              required: false
              type: string
            aliases:
              description: Aliases that can also be used to refer to this entity.
              required: false
              type: list
            room:
              description: Hint for Google Assistant in which room this entity is.
              required: false
              type: string
{% endconfiguration %}

<p class='note'>
After setting up the cloud, if you make any device changes such as changing the name or adding a new device simply say "Ok Google, sync my devices" to get the changes to show up.
</p>
