---
title: Components
---

# Components

## Overview

Vitrail offers an helper for each component. You can use them in your views like this:

```erb
<%= vt_component_name(options) { "Content" } %>
```

You can also render the component with a block:

```erb
<%= vt_component_name(options) do %>
  Content
<% end %>
```

## Custom attributes

Majority of the components accept the following custom attributes:

### Class

You can add custom classes to the component by passing the `class` option.

```erb
<%= vt_component_name(class: "text-red-600") { "Content" } %>
```

### Data attributes

You can add custom data attributes to the component by passing the `data` option.

```erb
<%= vt_component_name(data: { controller: "dashboard" }) { "Content" } %>
```

### Id

You can add an id to the component by passing the `id` option.

```erb
<%= vt_component_name(id: "dashboard-title") { "Content" } %>
```
