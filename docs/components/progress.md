---
layout: page
title: Progress
---

Stylize the HTML5 `<progress>` element with a few extra classes and some crafty browser-specific CSS. Be sure to read up on the browser support.

### Example

{% example html %}
<progress class="progress" value="0" max="100">0%</progress>
<progress class="progress" value="25" max="100">25%</progress>
<progress class="progress" value="50" max="100">50%</progress>
<progress class="progress" value="75" max="100">75%</progress>
<progress class="progress" value="100" max="100">100%</progress>
{% endexample %}

### IE9 support

Internet Explorer 9 doesn't support the HTML5 `<progress>` element, but we can work around that.

{% example html %}
<progress class="progress" value="25" max="100">
  <div class="progress">
    <span class="progress-bar" style="width: 25%;">25%</span>
  </div>
</progress>
{% endexample %}

### Contextual alternatives

Progress bars use some of the same button and alert classes for consistent styles.

{% example html %}
<progress class="progress progress-success" value="25" max="100">25%</progress>
<progress class="progress progress-info" value="50" max="100">50%</progress>
<progress class="progress progress-warning" value="75" max="100">75%</progress>
<progress class="progress progress-danger" value="100" max="100">100%</progress>
{% endexample %}

### Striped

Uses a gradient to create a striped effect.

{% example html %}
<progress class="progress progress-striped" value="10" max="100">10%</progress>
<progress class="progress progress-striped progress-success" value="25" max="100">25%</progress>
<progress class="progress progress-striped progress-info" value="50" max="100">50%</progress>
<progress class="progress progress-striped progress-warning" value="75" max="100">75%</progress>
<progress class="progress progress-striped progress-danger" value="100" max="100">100%</progress>
{% endexample %}

The striped gradient can also be animated. Add <code>.progress-animated</code> to <code>.progress</code> to animate the stripes right to left via CSS3 animations.

**Animated progress bars do not work in IE9, older versions of Firefox, and Opera 12** as they don't support CSS3 animations.

{% example html %}
<progress class="progress progress-striped progress-animated" value="25" max="100">25%</progress>
{% endexample %}