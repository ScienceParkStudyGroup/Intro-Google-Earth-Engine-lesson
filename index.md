---
layout: workshop      # DON'T CHANGE THIS.
venue: "Introduction to Google Earth Engine"        # brief name of host site without address 
address: "Online course"      # full street address of workshop 
country: "nl"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "52"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "4"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Thursday 1 July 2021"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:30-17:00"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2021-07-01      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2021-07-01        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Johannes De Groeve"] # boxed
helper: ["Stacy Shinneman"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["s.shinneman@uva.nl"]    # boxed, comma-separated list of contact email addresses for the host
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}



{% comment %}
Check DC curriculum
{% endcomment %}

{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}

<p id="rooms">
  <strong>Online course:</strong> We will meet using Zoom. Each session will begin in the main room with a short presentation by the instructor to help you get started with the module. Participants will then go to breakout rooms to work together on the module in groups of 2-3. Instructors and helpers will be available at all times for questions and problem solving. Like other Carpentries workshops, you will be learning by "coding along". To do this, you will need to have both the window for R and the window for the Zoom video conference client open. In order to see both at once, we recommend using one of the following set up options: 1) two monitors, 2) two devices, or 3) divide your screen. This <a href="https://carpentries.org/blog/2020/06/online-workshop-logistics-and_screen-layouts/">blog post</a> includes detailed information on how to set up your screen to follow along during the workshop.

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody. If we can help making learning easier for
  you, please get in touch (using contact details below) and we will
  try our best to help.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<h2 id="code-of-conduct">Code of Conduct</h2>

<p>
Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>.This document also outlines how to report an incident if needed.
</p>

<p class="text-center">
  <a href="https://goo.gl/forms/KoUfO53Za3apOuOK2">
    <button type="button" class="btn btn-info">Report a Code of Conduct Incident</button>
  </a>
</p>
<hr/>


{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<h2 id="collaborative_notes">Collaborative Notes</h2>

<p>
We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
<hr/>
{% endif %}

<h2>Schedule</h2>

| Topic                                                     | Overview  	| 
|-----------------------------------------------------------|-------------|
| <a href="https://geohackweek.github.io/GoogleEarthEngine/00-access-javascript/"> GEE Access and JavaScript Tips | How do I get an account? What are some JavaScript basics? |
| [Introduction to Google Earth Engine](https://geohackweek.github.io/GoogleEarthEngine/01-introduction/) | What is Google Earth Engine? What are the strengths and limitations of this platform?|
| [Code Editor](https://geohackweek.github.io/GoogleEarthEngine/02-code-editor/) | What are the key features of the online code editor? Where can I go for help while learning GEE? How do I search for and import datasets? How do I create, share and save scripts? |
| [Accessing Satellite Imagery](https://geohackweek.github.io/GoogleEarthEngine/03-load-imagery/)| How do I acquire satellite imagery at regional scales? How can I make image mosaics? How can I use vector data? How do I export images?|
| [Temporal and Spatial Reducers](https://geohackweek.github.io/GoogleEarthEngine/04-reducers/)| How do I aggregate a time series of raster data over a time period? How do I summarize data by vector regions? How do I export tabular data summaries?|
| [Supervised Classification of Satellite Imagery](https://geohackweek.github.io/GoogleEarthEngine/05-classify-imagery/)| What machine learning techniques are available in GEE? How do I perform supervised classification of satellite imagery? How do I assess the accuracy of my classifier? How do I create my own geometries manually?|
| [Time Series](https://geohackweek.github.io/GoogleEarthEngine/06-time-series/)| How do I create a time series for a given location? How can I plot that time series within Google Earth Engine? How do I make that plot interactive?|
| [Wrap-Up](https://geohackweek.github.io/GoogleEarthEngine/07-wrap-up/)| What are the most important GEE resources? Where do I find answers to my questions about GEE? What is happening under the hood in Earth Engine?|

<h2>Credits</h2>
All geohackweek instructional material is made available under the <a href="https://creativecommons.org/licenses/by/4.0/"> Creative Commons Attribution license.

{% comment %}
SCHEDULE

<div class="row">
  <div class="col-md-6">
    <h3>Schedule</h3>
    <table class="table table-striped">
      <tr>
        <td>Morning<br>(9:30-10:15)</td>
        <td><a href="https://datacarpentry.org/organization-geospatial/">Introduction to geospatial concepts and the datasets<br>(Stacy)</a>
        </td>
      </tr>
      <tr>
        <td>Morning<br>(10:15-11:15)</td>
        <td><a href="https://datacarpentry.org/r-raster-vector-geospatial/01-raster-structure/index.html">Intro to raster data<br>(Stacy)</a>
        </td>
      </tr>
      <tr>
        <td>Morning<br>(11:30-12:30)</td>
        <td><a href="https://datacarpentry.org/r-raster-vector-geospatial/02-raster-plot/index.html">Plot raster data<br>(Stacy)</a>
        </td>
      </tr>
      <tr>
        <td>Break</td>
	      <td>  </td>
      </tr>
      <tr>
        <td>Afternoon<br>(13:30-14:30)</td>
        <td><a href="https://datacarpentry.org/r-raster-vector-geospatial/03-raster-reproject-in-r/index.html">Reproject raster data<br>(Johannes)</a>
        </td>
      </tr>
      <tr>
        <td>Afternoon<br>(14:45-17:00)</td>
        <td><a href="https://datacarpentry.org/r-raster-vector-geospatial/04-raster-calculations-in-r/index.html">Raster calculations<br>(Johannes)</a>
        </td>
      </tr>
	 <tr>
        <td>Afternoon<br>(14:45-17:00)</td>
        <td><a href="https://datacarpentry.org/r-raster-vector-geospatial/05-raster-multi-band-in-r/index.html">Work with multi-band rasters<br>(Johannes)</a>
        </td>
      </tr>
    </table>
  </div>
{% endcomment %}
{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if site.carpentry == "swc" %}
{% include swc/syllabus.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}
