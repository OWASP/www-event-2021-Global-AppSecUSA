---

title: Schedule & Trainings
layout: event_noheader
permalink: /trainings/

---

# {{ page.title }}
<br>

**Training subject to change based on trainer availability.**<br>
3-day Training courses will be held virtually November 8-10<br>
2-day Training courses will be held virtually November 9-10<br>
1-day Training courses will be held virtually November 10 **with the exception of "Threat Modeling: A Master Class" which will be held on Nov. 9.**<br>
All courses will be virtual, beginning at 9amPT and will run until 5pmPT.
{% if site.data.trainings.size > 0 %}
{% assign trainings = site.data.trainings | sort: 'Title' %}
{% for trainer in trainings %}
<section class="trainer-section" id="{{trainer.SectionId}}">
<hr>
<ul>
<li><h3 class='training-header'>{{ trainer.Title }}<button class="cta-button grey" {%if trainer.Status == 'Postponed' or trainer.Status == 'Canceled' or trainer.Status == 'Booked Out' %}disabled='true' {%endif%} onclick="location.href='{{trainer.URL}}';" style="margin-left:1em;cursor: pointer;max-width=80px;">{%if trainer.Status == 'Postponed' or trainer.Status == 'Canceled' or trainer.Status == 'Booked Out'%}{{trainer.Status}}{%else%}Join Us{%endif%}</button></h3></li>
<li class="training-desc">{{ trainer.Description | markdownify }}</li>
    <ul>
        {% for tr in trainer.Trainers %}
        <li><div class="training-container"><a href="/trainers/#{{tr.TrainerId}}" title="{{tr.Biography | strip_html}}"><div class="training-image" style="background-image:url('{{tr.Image}}');"></div>{{tr.Name}}</a></div></li>
        {% endfor %}
    </ul>
</ul>
</section>
{% endfor %}
{% endif %}
