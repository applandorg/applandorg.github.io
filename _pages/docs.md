---
layout: default
title: Documentation
permalink: /documentation/
---
---
__Documentation__

- [Recording AppMaps with Ruby](#recording-appmaps-with-ruby)
- [Recording AppMaps with Java](#recording-appmaps-with-java)
- [Recording AppMaps with the AppLand browser extension](#recording-appmaps-with-the-appland-browser-extension)

---

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
<br/>

# Recording AppMaps with Java 

---

## Step 1: Install the AppMap Java agent

---

Download the most recent __appmap.jar__ from [GitHub](https://github.com/applandinc/appmap-java/releases) to your __$HOME__ directory (or other suitable directory) to use in your project.

## Step 2: Configure your project

---

Create a file called __appmap.yml__ in the root directory of your project. When you run your program, the appmap agent will read configuration settings from this file.

A sample configuration file for a typical Java project is provided below.

```
name: my-app
packages:
- path: com.mycorp.myproject
If you are adding maps to an application set that someone in your organization is already tracking with AppLand, then the application name you specify here and the application name in AppLand must match exactly. If you have any questions about this, contact your AppLand administrator.
```

Code that doesn’t match a path entry in appmap.yml is not recorded. It’s basically a way to tell AppLand which code is “your code” vs “other / library code”

| `name`           | Provides the project name (required)
| `packages`       | A list of Java packages and/or classes which will be recorded

Each entry in the packages list is a YAML object which has the following keys:

| `path`     | The name of a package or class to record. Sub-packages of each listed package will also be recorded. Example: `org.mycorp.myproject`.
| `exclude`  | A list of classes and/or packages to ignore. This setting is used to exclude a particular class or package to skip. Example: `org.mycorp.myproject.MyClass` .

## Step 3: Record AppMaps

---

The AppMap recorder is run as a Java agent. It must be started along with the JVM. This is typically done by passing the -javaagent argument to your JVM.

For example, running a raw Java command:

```
java -javaagent:$HOME/appmap.jar <java command arguments>
```
Using Maven:

```
$ mvn -DargLine="-javaagent:$HOME/appmap.jar" test
```
Maven with Surefire:

```
<plugin>
  <artifactID>maven-surefire-plugin</artifactID>
  <configuration>
    <argLine>-javaagent:${user.home}/appmap.jar</argLine>
  </configuration>
</plugin>
```
Gradle:

```
test {
  systemProperty 'appmap.debug', true
  systemProperty 'appmap.config.file', "$rootDir/appmap.yml"
  jvmArgs "-javaagent:$rootDir/appmap.jar"
}
```

### Recording test cases
When running test cases with the agent attached to the JVM, methods marked with JUnit's __@Test__ annotation will be recorded. A new __appmap.json__ file will be created for each unique test case.

To disable AppMap for a particular JUnit test (for example, a performance test), list the class or methods under an exclude in appmap.yml. By default each test will output an __appmap.json__ data file to the current working directory.

To specify the output directory for __appmap.json__ files, use the Java system property __appmap.output.directory__ .

<br/>
  
# Recording AppMaps with the AppLand browser extension
--- 

## Overview
---
AppLand "remote recording" is an easy way to record and analyze end-user flows for applications with a web-based UI. Remote recording is composed of two parts:

- The AppLand client for your programming language, which runs on the server side and makes the actual recordings of the code. To review setup instructions for the AppLand client, review the client setup instructions for [Ruby](#recording-appmaps-with-ruby) or [Java](#recording-appmaps-with-java).
- A browser extension which is used to start and finish recordings.

This guide assumes that you have the AppLand client installed and running with your application server code. By following the steps shown here, you will install the browser extension and use it to create, upload and view an AppMap.

## Step 1: Install the AppLand browser extension
---
Install the AppLand browser extension for either [Chrome](https://chrome.google.com/webstore/detail/appland/pgicekejplaefmcfiehhpiambdalpgmj) or [Firefox](https://addons.mozilla.org/en-US/firefox/addon/appland/).
You will now see the AppLand logo displayed in your extensions area.
Step 2: Enable AppLand remote recording for your project

***Don't enable AppLand remote recording in production. AppLand remote recording will serve recording results to any client request, without authentication.***

### Ruby

Add the AppMap remote recording middleware.

For example, in `config/initializers/appmap_remote_recording.rb` :

```
require 'appmap/middleware/remote_recording'

if Rails.env.development?
Rails.application.config.middleware.insert_after \
  Rails::Rack::Logger,
  AppMap::Middleware::RemoteRecording
end
```
Start your Rails server.

For example:
```
$ bundle exec rails server
```
###Java

When you run a Java process with the `appmap.jar` agent loaded, it will automatically enable remote recording.

Do not load `appmap.jar` in production environments.

## Step 3: Record an AppMap
---
Recording an appmap is easy.

1. Click on the appland icon next to the search bar in the head of your browser. This will open a small window.
2. Push the red round button to start recording.
3. Use your application as you normally would. Go through an end-user flow that you would like to analyze. As you click around and do stuff in your application, AppLand records what is happening on the back end.
4. When you are finished using your app, open the AppMap browser extension again. And push the red square button to stop recording.
5. The recording will be transferred to the AppLand website opened. A new browser tab will open on app.land.

## Step 4: Open the AppMap in AppLand
---
When you stop recording your appmap will open in a new browser tab automatically. This may take a minute to render depending on the size of the recording you made. When you upload the scenario, you may want to assign it a descriptive name and other attributes that will help you find it in the future.
