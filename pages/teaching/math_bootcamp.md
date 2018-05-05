---
layout: page
title: Math Bootcamp
sidebar_link: false
permalink: /teaching/math_bootcamp
---
<!--make new sidebar with reading, syllabus, etc-->

<a name="read"></a>

### Readings

<table class="table table-striped">
<thead>
    <tr>
        <th>Week</th>
        <th>Notes</th>
        <th>Simon & Blume</th>
    </tr>
</thead>
{% for reading in site.data.math_bootcamp.readings %}
<tr>
    <td>{{ reading.name }}</td>
    <td>
    {% for note in reading.notes %}
        <a class="btn btn-default" href="{{page.assets}}{{note.link}}">
        <i class="fa fa-download"></i>&nbsp; {{note.name}}</a>
    {% endfor %}
    {% if reading.ext_links %}
    <br/><b>External Resources</b>
        <ul>
        {% for link in reading.ext_links %}
            <li><a href="{{link.link}}">{{link.link}}</a></li>
        {% endfor %}
        </ul>
    {% endif %}
    </td>
    <td>{{reading.simonblume}}</td>
</tr>
{% endfor %}
</table>


<a name="assign"></a>

### Assignments

<table class="table table-striped">
{% for assignment in site.data.math_bootcamp.assignments %}
<tr>
    <td>
    <a class="btn btn-default" href="{{page.assets}}{{assignment.link}}">
        <i class="fa fa-download"></i>&nbsp; {{assignment.name}}</a>&nbsp;
    <span style="color:red; font-weight:bold;">Due: {{assignment.due}}</span>
    <p>{{assignment.descrip}}</p>
   {% for link in assignment.keys %} 
    <a style="background-color:#b0b0b0;" class="btn btn-default btn-sm" href="{{page.assets}}{{link.link}}"><i class="fa fa-key">&nbsp; {{link.name}}</i></a> 
   {% endfor %}
    </td>
</tr>
{% endfor %}
</table>