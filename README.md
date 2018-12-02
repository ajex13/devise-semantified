# Devise::Semantified

Generate devise views styled with semantic-ui.

## Installation

dependencies :

```ruby
gem 'semantic-ui-sass', git: 'https://github.com/doabit/semantic-ui-sass.git'
```

Add this line to your application's Gemfile:

```ruby
gem 'devise-semantified', git: 'https://github.com/ajex13/devise-semantified.git'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install devise-semantified

## Usage


After installing devise run this generator to get semantic-ui styled views.


  $ rails g devise:views:semantified

and also add this to 'app/assets/stylesheets/application.css.scss'


```ruby
.field_with_errors {
  @extend .field;
  @extend .error;
}
```

optional navbar for better navigation :


```ruby
<div class="ui top inverted menu">
  <a href="#" class="item"><strong>BrandName</strong></a>
  <%= link_to "Home", root_path, class: "active blue item" %>
  <a class="item">
    About
  </a>
  <a class="item">
    Contact
  </a>
  <div class="right menu">
    <% if user_signed_in?  %>
    <%= link_to  new_user_registration_path ,class: "item" do%>
      <i class="signup icon"></i> Sign Up
    <% end %>
    <%= link_to  new_user_session_path, class: "item" do %>
      <i class="sign in icon"></i> Login
    <% end %>
    <% else %>
    <%= link_to  edit_user_registration_path , class: "item" do %>
      <i class="settings icon"></i> Settings
    <% end %>

    <%= link_to  destroy_user_session_path ,method: :delete, data: {confirm: "Are you sure?"}, class: "item" do %>
      <i class="sign out icon"></i> Logout
    <% end %>

    <% end %>
  </div>
</div>
```


## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/devise-semantified. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
