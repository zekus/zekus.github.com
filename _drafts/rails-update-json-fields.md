---
layout: post
title: rails update json fields
---

model with json field
```ruby
the model
```

permit parameters

```ruby
def permitted_params
  data_keys = params.try(:fetch, :scanned_pig_event, {}).try(:fetch, :data, {}).keys
  params.permit(:id, :page, :scanned_pig_id, scanned_pig_event: [ data: data_keys ])
end
```

the form

```ruby
= simple_form_for @scanned_pig_event, url: [@scanned_pig_event.scanned_pig, @scanned_pig_event] do |f|
  = f.error_notification

  = f.simple_fields_for(:data, OpenStruct.new(@scanned_pig_event.data)) do |ff|
    - @scanned_pig_event.data.each do |k, v|
      = ff.input k.to_sym

```

happy coding!

