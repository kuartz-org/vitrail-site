---
title: Installation
---



# Installation

## Prerequisites
- Ruby v3
- Rails v7
- ViewComponent v3
- tailwindcss-rails (the gem) v2

In your Gemfile, add this line:
```ruby
gem "vitrail", "~> 1.0"
```

Then, run `bundle install`.

Finally, run the following command to install Vitrail's assets and configuration files in your project:
```bash
rails vitrail:install
```

This will:
- Add default styles to the available Vitrail classes in `lib/assets/stylesheets/vitrail`
- Add the Tailwind preset file in `lib/assets/vitrail_preset.js`
- Load the Vitrail styles in your `application.tailwind.css` file
- Add config to your `tailwind.config.js` file
