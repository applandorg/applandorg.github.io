---
layout: default
title: Ruby client
permalink: /documentation/ruby_client
---

{% include documentation_navigation.md%}

# Recording AppMaps with Ruby

## Step 1: Install the AppMap gem

---

Add `gem 'appmap'` to your Gemfile just as you would any other dependency.

```
gem 'appmap'
```

If you want to segregate installation to development or test environment use:

```
group :development, :test do
  gem 'appmap'
end
```
Then run `bundle install` .

## Step 2: Configure your project

---

Create a file called `appmap.yml` in the root directory of your project.

When you run your program, the appmap gem will read configuration settings from this file. A sample configuration file for a typical Rails project is provided below.

```
name: my-app
packages:
- path: app/controllers
- path: app/models
```

If you are adding maps to an application set that someone in your organization is already tracking with AppLand, then the application name you specify here and the application name in AppLand must match exactly. If you have any questions about this, contact your AppLand administrator.

## Step 3: Enable AppMaps for your RSpec tests

---

AppLand leverages existing test cases as a way to record running code. To instrument RSpec tests, require `appmap/rspec` in your `spec_helper.rb` :

```
require 'appmap/rspec'
```

## Step 4: Record AppMaps

--- 

Run tests with the environment variable `APPMAP=true`

```
$ APPMAP=true bundle exec rspec spec/my_test_spec.rb
```
Each RSpec test will output a data file into the directory tmp/appmap/rspec For example:

```
$ find tmp/appmap/rspec
my_app_behaves_as_expected.appmap.json  
```  