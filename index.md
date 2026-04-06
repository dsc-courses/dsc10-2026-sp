---
layout: home
title: 🏠 Home
nav_exclude: false
nav_order: 1
---

# {{ site.tagline }}

{: .mb-2 }
{{ site.description }}
{: .fs-6 .fw-300 }

{{ site.staffersnobio }}


{: .success }
>Welcome to DSC 10! Make sure to read this website thoroughly and complete the items in the [Getting Started](https://dsc10.com/syllabus/#-getting-started) checklist. These are due very soon, on **Thursday, April 2nd at 11:59PM**.

<!--{: .warning }
This site is **under construction**. Anything you read here is not finalized. This disclaimer will be removed when the site is ready for Spring 2026.-->

<!--{: .success }
>The Final Exam is **this Saturday, June 7th from 11:30AM to 2:30PM in CENTER 101**.
>
>Earn 1 participation point by filling out both [SETs](https://academicaffairs.ucsd.edu/Modules/Evals/) and the internal [End-of-Quarter Survey](https://forms.gle/hWqgRBp4B45LDMLW9) before Saturday, June 7th at 8AM.
-->

<!--{: .success }
>**Tip**: When working on assignments, use Ctrl+F on this page to search for a keyword and quickly find the relevant lecture. Click the "✏️ write" button to open a static version of the lecture for reference, which is much faster than loading it on DataHub.
>
>Also, make sure to use the [reference sheet]({{site.urls.reference}}) to quickly look up `babypandas` methods and see examples of how they work.
-->

<a id="jump-to-current-week" href="/#{{ site.modules.first.title | slugify }}" class="btn">Jump to the current week</a>
<script>
(function() {
  var weeks = [{% for module in site.modules %}{"slug":"{{ module.title | slugify }}","start":"{{ module.days.first.date | date: '%Y-%m-%d' }}"}{% unless forloop.last %},{% endunless %}{% endfor %}];
  var today = new Date();
  today.setHours(0, 0, 0, 0);
  var target = weeks[0].slug;
  for (var i = 0; i < weeks.length; i++) {
    if (today >= new Date(weeks[i].start)) target = weeks[i].slug;
  }
  document.getElementById('jump-to-current-week').href = '/#' + target;
})();
</script>

{% for module in site.modules %}
{{ module }}
{% endfor %}
