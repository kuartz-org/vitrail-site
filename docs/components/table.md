---
table: Title
---

{% if jekyll.environment == "production" %}
  {% assign lookbook_url = site.lookbook_url %}
{% else %}
  {% assign lookbook_url = "http://localhost:3000" %}
{% endif %}


# Table

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TablePreview"
  scenario="standard"
  actions="inspect">
</lookbook-embed>

## Usage

**ERB**

```erb
<%= vt_table do |table| %>
  <% table.with_header.with_content("#") %>
  <% table.with_header.with_content("Name") %>
  <% table.with_header.with_content("Email") %>

  <% users.each do |user| %>
    <% table.with_row do |row| %>
      <% row.with_division.with_content(user.id) %>
      <% row.with_division.with_content(user.name) %>
      <% row.with_division.with_content(user.email) %>
    <% end %>
  <% end %>
<% end %>
```

**SLIM**

```slim
= vt_table do |table|
  - table.with_header.with_content("id")
  - table.with_header.with_content("name")
  - table.with_header.with_content("email")

  - users.each do |user|
    - table.with_row do |row|
      - row.with_division.with_content(user.id)
      - row.with_division.with_content(user.name)
      - row.with_division.with_content(user.email)
```

### Link for a row

You can add a link to a row by passing the `link_to` option to the `with_row` method.
This will create a link inside each `<td>` element of the row.

```erb
<%= vt_table do |table| %>
  <% table.with_header.with_content("#") %>
  <% table.with_header.with_content("Name") %>
  <% table.with_header.with_content("Email") %>

  <% users.each do |user| %>
    <% table.with_row(link_to: "/users/#{user.id}") do |row| %>
      <% row.with_division.with_content(user.id) %>
      <% row.with_division.with_content(user.name) %>
      <% row.with_division.with_content(user.email) %>
    <% end %>
  <% end %>
<% end %>
```

<lookbook-embed
  app="{{ lookbook_url }}"
  preview="TablePreview"
  scenario="with_link"
  actions="inspect">
</lookbook-embed>

### Custom attributes

For now it's not possible to add custom attributes to the `<table>` element but
you can add custom attributes to the `th`, `tr` and the `td` elements.

**Bonus:**
You can pass a `td: {}` parameter to `#with_row` method to add
attributes to all the divisions `td` without having to pass them to each.

#### `tr`: Class

It's not possible to add custom classes to the `tr` element.

#### `tr`:Data attributes

You can add custom data attributes to the `tr` element by passing the `data` option to the `with_row` method.

```erb
<% table.with_row(data: { id: user.id }) do |row| %>
```

#### `tr`: Id

You can add an id to the `tr` element by passing the `id` option to the `with_row` method.

```erb
<% table.with_row(id: "user-#{user.id}") do |row| %>
```

#### `td`: Class

You can add custom classes to the `td` element by passing the `class` option to the `with_division` method.

```erb
<% row.with_division(class: "text-right").with_content(user.id) %>
```

#### `td`: Data attributes

You can add custom data attributes to the `td` element by passing the `data` option to the `with_division` method.

```erb
<% row.with_division(data: { id: user.id }).with_content(user.id) %>
```

#### `td`: Id

You can add an id to the `td` element by passing the `id` option to the `with_division` method.

```erb
<% row.with_division(id: "user-id-#{user.id}").with_content(user.id) %>
```
