### Instrumental
---
https://github.com/Instrumental

#### instrumental_agent-ruby
```
gem 'instrumental_agent'

```

```ruby
I = Instrumental::Agent.new('PROJECT_API_TOKEN', :enabled => Rails.env.production?)
I.gauge('load', 1.23)
I.increment('signups')
I.time('query_time') do
  post = Post.find(1)
end
I.time_ms('query_time_in_ms') do
  post = Post.find(1)
end

```

```

```


