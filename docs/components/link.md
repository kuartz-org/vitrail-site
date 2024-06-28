---
title: Link
---

{% if jekyll.environment == "production" %}
  {% assign lookbook_url = site.lookbook_url %}
{% else %}
  {% assign lookbook_url = "http://localhost:3000" %}
{% endif %}


# Link

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="LinkToPreview"
  scenario=""
  actions="inspect">
</lookbook-embed>

## Usage


```erb
<%= vt_link_to("/some/path") { "Go there" } %>
```

### Variant

You can render a link with a different variant by passing the `variant` option.

```erb
<%= vt_link_to("/some/path", variant: :secondary) { "Go there" } %>
```

Available variants are
- `:default`
- `:primary`
- `:secondary`
- `:outline`
- `:ghost`

### Behaves like the ActionView helper `link_to`

See [ActionView#link_to documentation](https://api.rubyonrails.org/classes/ActionView/Helpers/UrlHelper.html#method-i-link_to)
