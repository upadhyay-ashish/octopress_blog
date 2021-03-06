---           
layout: post
title: Export to Excel in Rails 3 without a Gem
date: 2011-11-29 21:02:54 UTC
updated: 2011-11-29 21:02:54 UTC
comments: true
categories: excel export rails xls export rails excel export rails 3 excel export ror xls export in ror xls export rails 3 xls export in ruby excel export ruby
---

+ Creating Demo project
{% highlight ruby linenos %}
	rails new xcel_demo –d mysql

{% endhighlight %}

+ Creating a User model
{% highlight ruby linenos %}
	rails g scaffold User name:string email:string content:string

{% endhighlight %}
+ Add a MIME type in \config\initializers\mime_type.rb
{% highlight ruby linenos %}
	Mime::Type.register 'application/vnd.ms-excel', :xls

{% endhighlight %}
+ Add a xls format output to the method in the Controller
{% highlight ruby linenos %}
		def index
	  @users = User.all
	  respond_to do |format|
	    format.html # index.html.erb
	    format.xls
	    format.xml  { render :xml => @users }
	  end
	end
		
{% endhighlight %}

+ Creating the view for the XLS

+ Now create a view to render the xls file. Here as we have modified the index method we will create a view index.xls.erb for the same in the views for Users
{% highlight ruby linenos %}
	<h1>Listing users</h1>

	<table>
	  <tr>
	    <th>Name</th>
	    <th>City</th>
	    <th>Gender</th>
	    <th>Phone</th>
	    <th>Address</th>
	    <th></th>
	    <th></th>
	    <th></th>
	  </tr>

	<% @users.each do |user| %>
	  <tr>
	    <td><%= user.name %></td>
	    <td><%= user.city %></td>
	    <td><%= user.gender %></td>
	    <td><%= user.phone %></td>
	    <td><%= user.address %></td>
	  </tr>
	<% end %>
	</table>

	<br />

{% endhighlight %}
+ The text in the <th> tags are the headers and <td> tags are the data for the specified columns
+ Adding the link to export excel on the Index page
{% highlight ruby linenos %}
    `<%= link_to 'Export XLS', url_for(:format => 'xls') %>`

{% endhighlight %}
+ This will allow the data on index page to be exported in Excel Format