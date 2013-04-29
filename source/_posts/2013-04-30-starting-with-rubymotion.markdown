---
layout: post
title: "Starting With Rubymotion"
date: 2013-04-30 01:17
comments: true
categories: rubymotion ios ruby cocoa
---

### [Rubymotion](http://www.rubymotion.com)

> RubyMotion is a revolutionary toolchain for iOS.
It lets you quickly develop and test native iOS applications for iPhone or iPad, all using the awesome Ruby language you know and love. 

----

 *To start with Rubymotion we would need*

+ A Mac 
+ Ruby
+ xCode 
+ Command Line Build Tools
+ Rubymotion
+ Text editor
+ Little knowledge of the Cocoa API's
+ Faith, Hope and Goodwill !

----
Assumming that the setup is done without any issues, Lets start 

*Check for an update for the Rubymotion installer*
```
sudo motion update
```
![Alt Icon](/images/rubymotion/rm-update.png)

*Creating our first application*
```
motion create RssReader
```

![Alt Icon](/images/rubymotion/rm-create.png)

*Structure of the Rubymotion application*
![Alt Icon](/images/rubymotion/rm-structure.png)

*Explaining the structure of the application*
```
app_delegate.rb 		 : Entry point of an iOS application
Default-568h@2x.png 	: Default Splash Screen for iPhone5
main_spec.rb 			sd: Main spec file
Rakefile 				: Application configuration
```
*Running the application on the Simulator*

```
rake
```

![Alt Icon](/images/rubymotion/rm-simulator.png)

> So this is the first very basic application which we have put up and running on a simulator.
> I will be moving step by step from the basics of using Ruby alongwith Cocoa and creating a Demo application throught it.

----
> Thanks

