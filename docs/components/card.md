---
title: Card
---

{% if jekyll.environment == "production" %}
  {% assign lookbook_url = site.lookbook_url %}
{% else %}
  {% assign lookbook_url = "http://localhost:3000" %}
{% endif %}

# Card

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="CardPreview"
  scenario="standard"
  panels="source, output">
</lookbook-embed>

## Usage

```erb
<%= vt_card do %>
  <p>Card content</p>
<% end %>
```

### With title


```erb
<%= vt_card do |card| %>
  <% card.with_title { "Card with title" } %>
  <p>Some content.</p>
<% end %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="CardPreview"
  scenario="with_title"
  panels="output">
</lookbook-embed>

### With description

```erb
<%= vt_card do |card| %>
  <% card.with_title { "Notifications" } %>
  <% card.with_description { "You have 3 unread messages." } %>
<% end %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="CardPreview"
  scenario="with_description"
  panels="output">
</lookbook-embed>

### With footer

```erb
<%= vt_card do |card| %>
  <p>Some content</p>
  <% card.with_footer { "Updated 10 minutes ago" } %>
<% end %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="CardPreview"
  scenario="with_footer"
  panels="output">
</lookbook-embed>


### Custom attributes

Card component doesn't accept custom attributes yet.

<!-- #### Class -->

<!-- You can add custom classes to the card component by passing the `class` option.

```erb
<%= vt_card(class: "bg-red-100 border-red-200 text-red-800") { "Something went wrong" } %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="CardPreview"
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
</lookbook-embed> -->
