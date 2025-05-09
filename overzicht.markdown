---
layout: home
title: Overzicht
permalink: /overzicht/
---

#  Overzicht P4 2024-2025
{: .text-green-200}
* 5 mei: Bevrijdingsdag
* 6 mei: Studiedag
* 29 mei: Hemelvaart
* 30 mei: Studiedag
* 9 juni: Pinksteren
* 30 juni: Laatste week
* 7 juli: Lesvrij *(geen vakantie)*

{% for lesson in site.data.lessons %}
## Les {{ lesson.number }}:  {{ lesson.title }}
{{ lesson.description }}
{% endfor %}


