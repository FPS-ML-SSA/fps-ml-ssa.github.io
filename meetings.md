---
layout: page
title: Meetings
permalink: /meetings.html
---

Below is a list of FPS-ML-SSA meetings. Select a meeting title for its details.

<ul class="meeting-list">
{% assign sorted_meetings = site.meetings | sort: 'date' | reverse %}
{% for meeting in sorted_meetings %}
  {% assign start_day = meeting.date | date: "%d" %}
  {% assign end_day = meeting.date_end | date: "%d" %}
  {% assign month = meeting.date | date: "%b" %}
  {% assign year = meeting.date | date: "%Y" %}
  <li>
    <a href="{{ meeting.url }}">{{ meeting.title }}</a>,
    {% if meeting.date_end %}
      {{ start_day }}-{{ end_day }} {{ month }} {{ year }}
    {% else %}
      {{ start_day }} {{ month }} {{ year }}
    {% endif %}
    {% if meeting.location %} ({{ meeting.location }}){% endif %}
  </li>
{% endfor %}
</ul>
