---
layout: default
title: Introduction to the Tiny Drive plugin APIs
title_nav: Introduction to the plugin APIs
description: Overview of the Tiny Drive plugin APIs
keywords: rtc configuration
---

The {{site.cloudfilemanager}} {{site.productname}} plugin includes APIs to provide access to {{site.cloudfilemanager}} from your custom plugins or {{site.productname}} specific integration code. These APIs are available though the `editor.plugins.tinydrive` property.

The {{site.cloudfilemanager}} plugin provides the following APIs:

- The Upload API
- The Browse API
- The Pick API

Select one of the following pages for details on using the {{site.cloudfilemanager}} plugin APIs:

{% assign navigation = site.data.nav %}
{% for entry in navigation %}
  {% if entry.url == "plugins" %}
    {% for subentry in entry.pages %}
      {% if subentry.url == "premium" %}
        {% for subsubentry in subentry.pages %}
          {% if subsubentry.url == "tinydrive" %}
            {% for sub3entry in subsubentry.pages %}
              {% if sub3entry.url == "apis" %}
                {% assign links = sub3entry.pages %}
              {% endif %}
            {% endfor %}
          {% endif %}
        {% endfor %}
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% include sub-level-toc.html links=links %}