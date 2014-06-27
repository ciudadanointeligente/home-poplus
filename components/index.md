---
layout: inner-page
title: Components
---

##Poplus Components: What are they?

Poplus Components are independent pieces of software developed to solve a range of common problems encountered when building civic and democratic websites.

These common problems include tasks like:

* Making and maintaining up-to-date data on politicians
* Working out what district, city or region a particular problem or politician relates to

Using Poplus Components, mixed with your own code, it becomes much less time
consuming to build and then maintain a variety of apps and sites. For example,
[this Parliamentary Monitoring site in South Africa](http://www.pa.org.za) uses
two Poplus Components - [SayIt](http://sayit.mysociety.org/) and
[MapIt](http://code.mapit.mysociety.org/).

This is a very high-level description of what a Poplus Component is. For a much more detailed description, see below.

##Why use a Poplus Component?

Do you have too much time? Or perhaps too much money? Or too many friends who are coders and designers?

If not, then you might want to use Poplus Components to help power your new democratic & civic website or app. They’re all about saving weeks or months of development time, without saying ‘You *must* use this language’ or ‘You *must* use this application'.

Also, you might want to use a Poplus Component because they allow non-technical and technical people to collaborate more effectively. Non-technical people can use high-quality interfaces to add and manipulate data, which programmers can then suck into tools and apps to make them work.

##What Poplus Components exist at the moment?
Here are all the Poplus Components currently in existence. They vary between being very mature and brand new.

<div class="grid-row" id="components">
<!--
{% for post in site.categories.component %}
	--><div class="column-one-of-two">
		<div class="catalogue-item catalogue-item--poplus-component">
			<h3><a href="
				{% if post.component_url %}
					    {{ post.component_url }}
					{% else if post.repo %}
						{{ post.repo }}
					{% endif %}
			">{{ post.title }}</a></h3>
			<div class="catalogue-item__content">
				{% if post.excerpt %}
		    		<p>{{ post.excerpt }}</p>
	    		{% endif %}
		    	<div class="catalogue-links"><!-- <strong>Tags: </strong>{{ post.tags | array_to_sentence_string }}<br> -->
		    		{% if post.component_url %}
					    <a href="{{ post.component_url }}">Website</a>
					{% else if post.repo %}
						<a href="{{ post.repo }}">Github repository</a>
					{% endif %}
				</div>
			</div>
		</div>
	</div><!--
{% endfor %}
-->
</div>


##Definition of a Poplus Component - v0.01
One of the most important things that happened at [PoplusCon](/popluscon/) was an agreement about what characteristics a piece of code has to have before it can be called a Poplus Component.

This page represents a v.01 spec, as agreed by about twenty people from various organisations who were in the room at the time. If you’d like to debate it or improve it, please [join the mailing list](https://groups.google.com/forum/#!forum/poplus) and tell us what should be different in the next version.

###Seven things that make a Poplus Component
If your code fits every one of the points below, congratulations! It's a Component and eligible for the Poplus seal of approval.
<ul class="tick-list" id="definition">
<li> My code helps Civic/Democratic websites </li>
<li> It solves a Single Problem</li>
<li> It is Composable with other Poplus Components</li>
<li> It's Platform Agnostic</li>
<li> It's Country Agnostic</li>
<li> It's Free/Open Source software</li>
<li> It has a stable, documented API</li>
</ul>
###What do these mean?
####Civic/Democratic
**Components work on websites that empower people in their civic or democratic lives**

Civic or democratic websites include sites that:
- Help ordinary people understand what is happening in their parliaments or governing bodies
- Enable citizens to contact the people and organisations that affect their lives
- Give people the power to effect changes in their own communities
- Highlight corruption and allow people to do something about it
- Facilitate transparency and enable the sharing of information

Typically, such sites are non-commercial, non-partisan and open to all.

Your Component may work well on sites that don't fit these guidelines, but it must also work on sites that do.

####Solves a Single Problem
**Each Component does just one thing**

Your Component should solve one problem for people who are running civic or democratic websites. If it does more than one thing, you should split it into different Components.

For example, there are Components which model bills. There are ones which model people, ones for votes, and ones for speeches. There are Components which allow people to contact politicians, others which let them send requests for information.

Each of these Components can work with the others, or independently.

Your Component might solve obvious problems, like storing names and positions of politicians. It should do so thoughtfully, and ideally it should be based on experience: your own experience, or the experiences of those who will use it.

So, it might help with tiny issues that most people would never think about - like that fact that politicians sometimes change their names. Thanks to your Component, people never need to think about it!

####Composable
**Components work with other Components**

This is one of the key elements of a Component (and it's where the name Component comes from) - it must work with any other Components. Components are like building blocks: you can put them together to create something bigger.

Standalone sites, or platforms for constructing them (e.g. [Alaveteli](http://www.alaveteli.org)) are very worthy pieces of software, but they are not Components.

####Platform Agnostic
**People should be able to use your Poplus Component on any website, no matter what platform they are using.**

Your Component can be written in any programming language or framework - that's because interaction should be over APIs (see below), so the underlying code isn't so important to the person implementing it. Write your Component in whatever language you are most comfortable with.

Ideally, your Component will be offered as a cloud or SAAS version: that makes it really easy for people to use it. At the same time, it should be relatively easy to install, configure and deploy, because many users will eventually want to run their own locally hosted version.

[Docker](http://docker.io) is one simple way of making this easier.

####Country Agnostic
**Components work everywhere**

Poplus was created so that organisations everywhere could share and collaborate on code. We exist so that people don't have to keep 'reinventing the wheel', or writing new code when they could use code that already exists.

So, as much as possible, it should be possible to deploy your Component anywhere in the world. That means making the minimum number of assumptions about political models and structures; it means that the interface and data should work in other languages (think Arabic and Russian, not just English and Spanish) and preferably in multiple languages simultaneously.

We recognise that it isn't easy to model every system in the world out of the box. If you can't manage all the above, strive for this: it should be simpler to adapt the Component for an entirely different country than to start again from scratch.

In many cases it will be worthwhile to work with groups in other countries on a suitable data standard before ever starting to code. The Poplus community can help you make those links.

#### Free/Open Source
**Your Component should embrace the spirit of Open Source**

When we talk about Open Source, we don't just mean that your Component should bear an Open Source licence (although, that part is essential).

Developing a Component means being open in every way. So your code should be on Github or an equivalent open source repository, with a public issue tracker that anyone can contribute to.

You should commit to maintaining your Component responsibly and responsively, and if you find that you are no longer able to do this, you should be prepared to hand it over to someone who can.

#### Stable, documented API
**Users should be able to rely on Components**

So that Components can work together, all functionality should be exposed over APIs. These APIs should be very-well documented, so that anyone can use them, and so that future contributors can work on them.

We recommend a REST-like HTTP API. If you don't know what that means, your developers should (or give us a shout on [our mailing list](https://groups.google.com/forum/#!forum/poplus)).

As other sites and Components will be relying on this, it is essential that the API is stable. New endpoints can be added, but existing ones should not disappear, or change meaning, without a version change, or going through a suitable deprecation cycle.


###Ticked all seven boxes?

Wonderful - you've made a Poplus Component. Please let us know, and we'll help you get the word out to the people who can use it.

Need some help getting there?

Drop a message to the [Poplus mailing list](https://groups.google.com/forum/#!forum/poplus) - there are many friendly coders there who can help you with queries or problems.
