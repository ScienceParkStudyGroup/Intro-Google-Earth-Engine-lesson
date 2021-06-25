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
helper: ["Zsophia Koma", "Stacy Shinneman"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
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
Eventbrite link can be added into _includes/workshop_ad.html in line starting <button style
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

<p id="description">
  <strong>Google Earth Engine</strong> combines a multi-petabyte catalog of satellite imagery and geospatial datasets with planetary-scale analysis capabilities and makes it available for scientists, researchers, and developers to detect changes, map trends, and quantify differences on the Earth's surface. It is also a tool for analyzing geospatial information. It has a searchable data catalog, including the entire EROS (USGS/NASA) Landsat catalog, numerous MODIS datasets, Sentinel-1 data, NAIP data, precipitation data, sea surface temperature data, CHIRPS climate data, and elevation data. Users can also upload their own data for analysis in Earth Engine, with full control over access.
</p> 

<p id="rooms">
  <strong>Online course:</strong> We will meet using Zoom. Each session will begin in the main room with a short presentation by the instructor to help you get started with the module. Participants will then go to breakout rooms to work together on the module in groups of 2-3. Instructors and helpers will be available at all times for questions and problem solving. Like other Carpentries workshops, you will be learning by "coding along". To do this, you will need to have both the window for R and the window for the Zoom video conference client open. In order to see both at once, we recommend using one of the following set up options: 1) two monitors, 2) two devices, or 3) divide your screen. This <a href="https://carpentries.org/blog/2020/06/online-workshop-logistics-and_screen-layouts/">blog post</a> includes detailed information on how to set up your screen to follow along during the workshop.
</p> 

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

{% comment%}
SCHEDULE
To make the table bigger or smaller, adjust the number in <div class="col-md-##">
{% endcomment %}

<h2>Schedule</h2>
<div class="row">
  <div class="col-md-12">
    <table class="table center">
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine-lesson/00-access-javascript/"> GEE Access and JavaScript Tips</a> </td>
        <td>How do I get an account? <br> What are some JavaScript basics?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine-lesson/01-introduction/"> Introduction to Google Earth Engine </a> </td>
        <td>What is Google Earth Engine? <br>What are the strengths and limitations of this platform?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/02-code-editor/"> Code Editor </a> </td>
        <td>What are the key features of the online code editor? <br>Where can I go for help while learning GEE? <br>How do I search for and import datasets? How do I create, share and save scripts?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/03-load-imagery/"> Accessing Satellite Imagery </a> </td>
        <td>How do I acquire satellite imagery at regional scales? <br>How can I make image mosaics? <br>How can I use vector data? <br>How do I export images?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/04-reducers/"> Temporal and Spatial Reducers </a> </td>
        <td>How do I aggregate a time series of raster data over a time period? <br>How do I summarize data by vector regions? <br>How do I export tabular data summaries?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/05-classify-imagery/"> Supervised Classification of Satellite Imagery </a> </td>
        <td>What machine learning techniques are available in GEE? <br>How do I perform supervised classification of satellite imagery? <br>How do I assess the accuracy of my        classifier? <br>How do I create my own geometries manually?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/06-time-series/"> Time Series </a> </td>
        <td>How do I create a time series for a given location? <br>How can I plot that time series within Google Earth Engine? <br>How do I make that plot interactive?
        </td>
        </tr>
      <tr>
        <td><a href="https://scienceparkstudygroup.github.io/GoogleEarthEngine/07-wrap-up/"> Wrap-Up </a> </td>
        <td> What are the most important GEE resources? <br>Where do I find answers to my questions about GEE? <br>What is happening under the hood in Earth Engine?
        </td>
        </tr>
    </table>
  </div>

{% comment%}
SETUP
{% endcomment %}

<h2 id="setup">Setup</h2>
  <p>
To get access to Earth Engine, please fill out the form at <a href="https://signup.earthengine.google.com">signup.earthengine.google.com</a>. A gmail is best if you have one. You will receive an email titled "Welcome to Google Earth Engine" with instructions for getting started.
  <p>

{% comment%}
CREDITS
{% endcomment %}

<h2>Credits</h2>
  <p>
All geohackweek instructional material is made available under the <a href="https://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution license</a>.




