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

I.synchronous = true
User.find_each do |user|
  I.increment('signups', 1, user.created_at)
end

set :instrumental_key, "MY_API_KE"

before "deploy", "instrumental:util:depoly_start"
after "deploy", "instrumental:util:deploy_end"
before "deploy:migrations", "instrumental:util:depoly_start"
after "deploy:migrations", "instrumental:util:deploy_end"
after "instrumental:util:deploy_end", "instrumental:record_deploy_notice"

```

```

```


