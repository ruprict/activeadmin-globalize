# ActiveAdmin::Globalize
Makes it easy to translate your resource fields.

## Context
The original gem is not maintened anymore, so I forked it to be compatible for Rails 4.2 and globalize 5 .

## Installation

```ruby
gem "activeadmin-globalize", github: 'anthony-robin/activeadmin-globalize'
```

## Your model

```ruby
active_admin_translates :title, :description do
  validates_presence_of :title
end
```
## Editor configuration

```ruby
# if you are using Rails 4 or Strong Parameters:
permit_params translations_attributes: [:locale, :title, :content]


index do
  # ...
  translation_status
  # ...
  default_actions
end

form do |f|
  # ...
  f.translated_inputs "Translated fields", switch_locale: false do |t|
    t.input :title
    t.input :content
  end
  # ...
end
```
If `switch_locale` is set, each tab will be rendered switching locale.

