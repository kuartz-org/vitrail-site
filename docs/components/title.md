---
title: Title
---

{% if jekyll.environment == "production" %}
  {% assign lookbook_url = site.lookbook_url %}
{% else %}
  {% assign lookbook_url = "http://localhost:3000" %}
{% endif %}


# Title

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TitlePreview"
  scenario="level_1, level_2, level_3, level_4"
  panels="source, output">
</lookbook-embed>


## Usage

By default level 1 title is rendered.

```erb
<%= vt_title { "Dashboard" } %>
```

You can also render level `2`, `3` and `4` titles.

```erb
<%= vt_title(level: 2) { "Dashboard" } %>
<%= vt_title(level: 3) { "Dashboard" } %>
<%= vt_title(level: 4) { "Dashboard" } %>
```


### Custom attributes

#### Class

You can add custom classes to the title component by passing the `class` option.

```erb
<%= vt_title(class: "text-red-600") { "Dashboard" } %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TitlePreview"
  scenario="with_custom_classes"
  panels="output">
</lookbook-embed>

#### Data attributes

You can add custom data attributes to the title component by passing the `data` option.

```erb
<%= vt_title(data: { controller: "dashboard" }) { "Dashboard" } %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TitlePreview"
  scenario="with_data_attributes"
  panels="output">
</lookbook-embed>

#### Id

You can add an id to the title component by passing the `id` option.

```erb
<%= vt_title(id: "dashboard-title") { "Dashboard" } %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TitlePreview"
  scenario="with_id"
  panels="output">
</lookbook-embed>

## Playground

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TitlePreview"
  scenario="playground"
  param-title="Dashboard"
  panels="params, output">
</lookbook-embed>
