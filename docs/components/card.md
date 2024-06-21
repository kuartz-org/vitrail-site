---
title: Card
---

# Card

## Default

```erb
<%= vt_card do %>
  <p>Card content</p>
<% end %>
```

## With title

```erb
<%= vt_card do |card| %>
  <% card.with_title { "Card title" } %>
  <p>Card content</p>
<% end %>
```
