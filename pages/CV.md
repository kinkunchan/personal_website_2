---
layout: single
classes: wide
author_profile: true
pdf_file: '../assets/files/JunchenJin_Resume_2307.pdf'
title: Curriculum Vitae
permalink: /cv/
---
<p class="page__date"><strong><i class="fas fa-fw fa-calendar-alt" aria-hidden="true"></i> {{ site.data.ui-text[site.locale].date_label | default: "Updated:" }}</strong> 
March. 31, 2023
</p>

{% pdf {{ page.pdf_file | uri_escape }} height=1000px %}

