---
layout: docs
title: Bootstrap list group
description: Bootstrap List Groups allows displaying are a series of content. Learn how to use Bootstrap list group to build complex list structure on your website.
group: components
aliases:
  - "/components/list-group/"
  - "/components/bootstrap/list-group/"
toc: true
bootstrap: true
---

## Basic example

The default list group is an unordered list with items and the proper CSS classes. Build upon it with the options that follow, or with your CSS as required.

{{< example >}}
<ul class="list-group">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{{< /example >}}

## Active items

Attach `.active` to a `.list-group-item` to show the current active selection.

{{< example >}}
<ul class="list-group">
  <li class="list-group-item active" aria-current="true">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{{< /example >}}

## Disabled items

Attach `.disabled` to a `.list-group-item` to make it appear disabled. Remark that some of the elements with `.disabled` will also require custom JavaScript to disable their click events (e.g., links).

{{< example >}}
<ul class="list-group">
  <li class="list-group-item disabled" aria-disabled="true">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{{< /example >}}

## Links and buttons

Use `<a>`s or `<button>`s to create _actionable_ list group items with hover, disabled, and active states by adding `.list-group-item-action`. We separate these pseudo-classes to ensure list groups made of non-interactive elements (like `<li>`s or `<div>`s) don't provide a click or tap affordance.

Be sure to **not use the standard `.btn` classes here**.

{{< example >}}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
    Cras justo odio
  </a>
  <a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>
  <a href="#" class="list-group-item list-group-item-action">Morbi leo risus</a>
  <a href="#" class="list-group-item list-group-item-action">Porta ac consectetur ac</a>
  <a href="#" class="list-group-item list-group-item-action disabled" tabindex="-1" aria-disabled="true">Vestibulum at eros</a>
</div>
{{< /example >}}

With `<button>`s, you can also make use of the `disabled` attribute instead of the `.disabled` class. Sadly, `<a>`s don't support the disabled attribute.

{{< example >}}
<div class="list-group">
  <button type="button" class="list-group-item list-group-item-action active" aria-current="true">
    Cras justo odio
  </button>
  <button type="button" class="list-group-item list-group-item-action">Dapibus ac facilisis in</button>
  <button type="button" class="list-group-item list-group-item-action">Morbi leo risus</button>
  <button type="button" class="list-group-item list-group-item-action">Porta ac consectetur ac</button>
  <button type="button" class="list-group-item list-group-item-action" disabled>Vestibulum at eros</button>
</div>
{{< /example >}}

## Flush

Add `.list-group-flush` to remove some borders and rounded corners to render list group items edge-to-edge in a parent container (e.g., cards).

{{< example >}}
<ul class="list-group list-group-flush">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
  <li class="list-group-item">Porta ac consectetur ac</li>
  <li class="list-group-item">Vestibulum at eros</li>
</ul>
{{< /example >}}

## Horizontal

Add `.list-group-horizontal` to change the layout of list group items from vertical to horizontal across all breakpoints. Alternatively, choose a responsive variant `.list-group-horizontal-{sm|md|lg|xl|xxl}` to make a list group horizontal starting at that breakpoint's `min-width`. Currently **horizontal list groups cannot be combined with flush list groups.**

**ProTip:** Want equal-width list group items when horizontal? Add `.flex-fill` to each list group item.

{{< example >}}
{{< list-group.inline >}}
{{- range $.Site.Data.breakpoints }}
<ul class="list-group list-group-horizontal{{ .abbr }}">
  <li class="list-group-item">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
</ul>
{{- end -}}
{{< /list-group.inline >}}
{{< /example >}}

## Contextual classes

Use contextual classes to style list items with a stateful background and color.

{{< example >}}
<ul class="list-group">
  <li class="list-group-item">Dapibus ac facilisis in</li>
{{< list.inline >}}
{{- range (index $.Site.Data "theme-colors") }}
  <li class="list-group-item list-group-item-{{ .name }}">A simple {{ .name }} list group item</li>
{{- end -}}
{{< /list.inline >}}
</ul>
{{< /example >}}

Contextual classes also work with `.list-group-item-action`. Note the addition of the hover styles here not present in the previous example. Also supported is the `.active` state; apply it to indicate an active selection on a contextual list group item.

{{< example >}}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action">Dapibus ac facilisis in</a>
{{< list.inline >}}
{{- range (index $.Site.Data "theme-colors") }}
  <a href="#" class="list-group-item list-group-item-action list-group-item-{{ .name }}">A simple {{ .name }} list group item</a>
{{- end -}}
{{< /list.inline >}}
</div>
{{< /example >}}

{{< callout info >}}
{{< partial "callout-warning-color-assistive-technologies.md" >}}
{{< /callout >}}

## With badges

Add badges to any list group item to show unread counts, activity, and more with the help of some [utilities]({{< docsref "/utilities/flex" >}}).

{{< example >}}
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Cras justo odio
    <span class="badge bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Dapibus ac facilisis in
    <span class="badge bg-primary rounded-pill">2</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Morbi leo risus
    <span class="badge bg-primary rounded-pill">1</span>
  </li>
</ul>
{{< /example >}}

## Custom content

Add nearly any HTML within, even for linked list groups like the one below, with the help of [flexbox utilities]({{< docsref "/utilities/flex" >}}).

{{< example >}}
<div class="list-group">
  <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small>3 days ago</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small>Donec id elit non mi porta.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-muted">3 days ago</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
  <a href="#" class="list-group-item list-group-item-action">
    <div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1">List group item heading</h5>
      <small class="text-muted">3 days ago</small>
    </div>
    <p class="mb-1">Donec id elit non mi porta gravida at eget metus. Maecenas sed diam eget risus varius blandit.</p>
    <small class="text-muted">Donec id elit non mi porta.</small>
  </a>
</div>
{{< /example >}}

## Checkboxes and radios

Place Bootstrap's checkboxes and radios within list group items and customize as needed. You can use them without `<label>`s, but please remember to include an `aria-label` attribute and value for accessibility.

{{< example >}}
<ul class="list-group">
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" aria-label="...">
    Cras justo odio
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" aria-label="...">
    Dapibus ac facilisis in
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" aria-label="...">
    Morbi leo risus
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" aria-label="...">
    Porta ac consectetur ac
  </li>
  <li class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="" aria-label="...">
    Vestibulum at eros
  </li>
</ul>
{{< /example >}}

And if you want `<label>`s as the `.list-group-item` for large hit areas, you can do that, too.

{{< example >}}
<div class="list-group">
  <label class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="">
    Cras justo odio
  </label>
  <label class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="">
    Dapibus ac facilisis in
  </label>
  <label class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="">
    Morbi leo risus
  </label>
  <label class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="">
    Porta ac consectetur ac
  </label>
  <label class="list-group-item">
    <input class="form-check-input me-1" type="checkbox" value="">
    Vestibulum at eros
  </label>
</div>
{{< /example >}}


## JavaScript behavior

Use the tab JavaScript plugin—include it individually or through the compiled `coreui.js` file—to extend our list group to create tabbable panes of local content.

<div class="docs-example" role="tabpanel">
  <div class="row">
    <div class="col-4">
      <div class="list-group" id="list-tab" role="tablist">
        <a class="list-group-item list-group-item-action active" id="list-home-list" data-coreui-toggle="tab" href="#list-home" role="tab" aria-controls="list-home">Home</a>
        <a class="list-group-item list-group-item-action" id="list-profile-list" data-coreui-toggle="tab" href="#list-profile" role="tab" aria-controls="list-profile">Profile</a>
        <a class="list-group-item list-group-item-action" id="list-messages-list" data-coreui-toggle="tab" href="#list-messages" role="tab" aria-controls="list-messages">Messages</a>
        <a class="list-group-item list-group-item-action" id="list-settings-list" data-coreui-toggle="tab" href="#list-settings" role="tab" aria-controls="list-settings">Settings</a>
      </div>
    </div>
    <div class="col-8">
      <div class="tab-content" id="nav-tabContent">
        <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">
          <p>Velit aute mollit ipsum ad dolor consectetur nulla officia culpa adipisicing exercitation fugiat tempor. Voluptate deserunt sit sunt nisi aliqua fugiat proident ea ut. Mollit voluptate reprehenderit occaecat nisi ad non minim tempor sunt voluptate consectetur exercitation id ut nulla. Ea et fugiat aliquip nostrud sunt incididunt consectetur culpa aliquip eiusmod dolor. Anim ad Lorem aliqua in cupidatat nisi enim eu nostrud do aliquip veniam minim.</p>
        </div>
        <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">
          <p>Cupidatat quis ad sint excepteur laborum in esse qui. Et excepteur consectetur ex nisi eu do cillum ad laborum. Mollit et eu officia dolore sunt Lorem culpa qui commodo velit ex amet id ex. Officia anim incididunt laboris deserunt anim aute dolor incididunt veniam aute dolore do exercitation. Dolor nisi culpa ex ad irure in elit eu dolore. Ad laboris ipsum reprehenderit irure non commodo enim culpa commodo veniam incididunt veniam ad.</p>
        </div>
        <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">
          <p>Ut ut do pariatur aliquip aliqua aliquip exercitation do nostrud commodo reprehenderit aute ipsum voluptate. Irure Lorem et laboris nostrud amet cupidatat cupidatat anim do ut velit mollit consequat enim tempor. Consectetur est minim nostrud nostrud consectetur irure labore voluptate irure. Ipsum id Lorem sit sint voluptate est pariatur eu ad cupidatat et deserunt culpa sit eiusmod deserunt. Consectetur et fugiat anim do eiusmod aliquip nulla laborum elit adipisicing pariatur cillum.</p>
        </div>
        <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">
          <p>Irure enim occaecat labore sit qui aliquip reprehenderit amet velit. Deserunt ullamco ex elit nostrud ut dolore nisi officia magna sit occaecat laboris sunt dolor. Nisi eu minim cillum occaecat aute est cupidatat aliqua labore aute occaecat ea aliquip sunt amet. Aute mollit dolor ut exercitation irure commodo non amet consectetur quis amet culpa. Quis ullamco nisi amet qui aute irure eu. Magna labore dolor quis ex labore id nostrud deserunt dolor eiusmod eu pariatur culpa mollit in irure.</p>
        </div>
      </div>
    </div>
  </div>
</div>

```html
<div class="row">
  <div class="col-4">
    <div class="list-group" id="list-tab" role="tablist">
      <a class="list-group-item list-group-item-action active" id="list-home-list" data-coreui-toggle="list" href="#list-home" role="tab" aria-controls="home">Home</a>
      <a class="list-group-item list-group-item-action" id="list-profile-list" data-coreui-toggle="list" href="#list-profile" role="tab" aria-controls="profile">Profile</a>
      <a class="list-group-item list-group-item-action" id="list-messages-list" data-coreui-toggle="list" href="#list-messages" role="tab" aria-controls="messages">Messages</a>
      <a class="list-group-item list-group-item-action" id="list-settings-list" data-coreui-toggle="list" href="#list-settings" role="tab" aria-controls="settings">Settings</a>
    </div>
  </div>
  <div class="col-8">
    <div class="tab-content" id="nav-tabContent">
      <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">...</div>
      <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">...</div>
      <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">...</div>
      <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">...</div>
    </div>
  </div>
</div>
```

### Using data attributes

You can activate a list group navigation without writing any JavaScript by simply specifying `data-coreui-toggle="list"` or on an element. Use these data attributes on `.list-group-item`.

```html
<div role="tabpanel">
  <!-- List group -->
  <div class="list-group" id="myList" role="tablist">
    <a class="list-group-item list-group-item-action active" data-coreui-toggle="list" href="#home" role="tab">Home</a>
    <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#profile" role="tab">Profile</a>
    <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#messages" role="tab">Messages</a>
    <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#settings" role="tab">Settings</a>
  </div>

  <!-- Tab panes -->
  <div class="tab-content">
    <div class="tab-pane active" id="home" role="tabpanel">...</div>
    <div class="tab-pane" id="profile" role="tabpanel">...</div>
    <div class="tab-pane" id="messages" role="tabpanel">...</div>
    <div class="tab-pane" id="settings" role="tabpanel">...</div>
  </div>
</div>
```

### Via JavaScript

Enable tabbable list item via JavaScript (each list item needs to be activated individually):

```js
var triggerTabList = [].slice.call(document.querySelectorAll('#myTab a'))
triggerTabList.forEach(function (triggerEl) {
  var tabTrigger = new coreui.Tab(triggerEl)

  triggerEl.addEventListener('click', function (event) {
    event.preventDefault()
    tabTrigger.show()
  })
})
```

You can activate individual list item in several ways:

```js
var triggerEl = document.querySelector('#myTab a[href="#profile"]')
coreui.Tab.getInstance(triggerEl).show() // Select tab by name

var triggerFirstTabEl = document.querySelector('#myTab li:first-child a')
coreui.Tab.getInstance(triggerFirstTabEl).show() // Select first tab
```

### Fade effect

To make tabs panel fade in, add `.fade` to each `.tab-pane`. The first tab pane must also have `.show` to make the initial content visible.

```html
<div class="tab-content">
  <div class="tab-pane fade show active" id="home" role="tabpanel">...</div>
  <div class="tab-pane fade" id="profile" role="tabpanel">...</div>
  <div class="tab-pane fade" id="messages" role="tabpanel">...</div>
  <div class="tab-pane fade" id="settings" role="tabpanel">...</div>
</div>
```

### Methods

#### constructor

Activates a list item element and content container. Tab should have either a `data-coreui-target` or an `href` targeting a container node in the DOM.

```html
<div class="list-group" id="myList" role="tablist">
  <a class="list-group-item list-group-item-action active" data-coreui-toggle="list" href="#home" role="tab">Home</a>
  <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#profile" role="tab">Profile</a>
  <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#messages" role="tab">Messages</a>
  <a class="list-group-item list-group-item-action" data-coreui-toggle="list" href="#settings" role="tab">Settings</a>
</div>

<div class="tab-content">
  <div class="tab-pane active" id="home" role="tabpanel">...</div>
  <div class="tab-pane" id="profile" role="tabpanel">...</div>
  <div class="tab-pane" id="messages" role="tabpanel">...</div>
  <div class="tab-pane" id="settings" role="tabpanel">...</div>
</div>

<script>
  var firstTabEl = document.querySelector('#myTab a:last-child')
  var firstTab = new coreui.Tab(firstTabEl)

  firstTab.show()
</script>
```

#### show

Selects the given list item and shows its associated pane. Any other list item that was previously selected becomes unselected and its associated pane is hidden. **Returns to the caller before the tab pane has actually been shown** (for example, before the `shown.coreui.tab` event occurs).

```js
  var someListItemEl = document.querySelector('#someListItem')
  var tab = new coreui.Tab(someListItemEl)

  tab.show()
```

#### dispose

Destroys an element's tab.

#### getInstance

*Static* method which allows you to get the tab instance associated with a DOM element

```js
var triggerEl = document.querySelector('#trigger')
var tab = coreui.Tab.getInstance(triggerEl) // Returns a Bootstrap tab instance
```

### Events

When showing a new tab, the events fire in the following order:

1. `hide.coreui.tab` (on the current active tab)
2. `show.coreui.tab` (on the to-be-shown tab)
3. `hidden.coreui.tab` (on the previous active tab, the same one as for the `hide.coreui.tab` event)
4. `shown.coreui.tab` (on the newly-active just-shown tab, the same one as for the `show.coreui.tab` event)

If no tab was already active, the `hide.coreui.tab` and `hidden.coreui.tab` events will not be fired.

<table class="table">
  <thead>
    <tr>
      <th style="width: 150px;">Event type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>show.coreui.tab</code></td>
      <td>This event fires on tab show, but before the new tab has been shown. Use <code>event.target</code> and <code>event.relatedTarget</code> to target the active tab and the previous active tab (if available) respectively.</td>
    </tr>
    <tr>
      <td><code>shown.coreui.tab</code></td>
      <td>This event fires on tab show after a tab has been shown. Use <code>event.target</code> and <code>event.relatedTarget</code> to target the active tab and the previous active tab (if available) respectively.</td>
    </tr>
    <tr>
      <td><code>hide.coreui.tab</code></td>
      <td>This event fires when a new tab is to be shown (and thus the previous active tab is to be hidden). Use <code>event.target</code> and <code>event.relatedTarget</code> to target the current active tab and the new soon-to-be-active tab, respectively.</td>
    </tr>
    <tr>
      <td><code>hidden.coreui.tab</code></td>
      <td>This event fires after a new tab is shown (and thus the previous active tab is hidden). Use <code>event.target</code> and <code>event.relatedTarget</code> to target the previous active tab and the new active tab, respectively.</td>
    </tr>
  </tbody>
</table>

```js
var tabEl = document.querySelector('a[data-coreui-toggle="list"]')
tabEl.addEventListener('shown.coreui.tab', function (event) {
  event.target // newly activated tab
  event.relatedTarget // previous active tab
})
```

## Customizing

### SASS
{{< scss-docs name="list-group-variables" file="scss/_variables.scss" >}}

#### Variants

CoreUI allows defining variant colors in two ways.

Check out [our Sass maps and loops docs]({{< docsref "/customize/sass#maps-and-loops" >}}) for how to customize these loops and extend CoreUI's base-modifier approach to your own code.

##### Manual

You can define each color manually and keep full control of the component appearance.

{{< highlight scss >}}
$alert-variants: (
  "primary": (
    "background": $your-bg-color,
    "background-hover": $your-bg-hover-color,
    "color": $your-color
  )
  ...
);
{{< /highlight >}}

##### Color function

The color set can be generated automatically thanks to our `list-group-color-map` function.

{{< scss-docs name="list-group-color-functions" file="scss/_functions.scss" >}}

{{< highlight scss >}}
$alert-variants: (
  "primary": alert-color-map($primary),
  ...
);
{{< /highlight >}}

#### Modifiers

CoreUI's list group component is built with a base-modifier class approach. This means the bulk of the styling is contained to a base class `.list-group-item` while style variations are confined to modifier classes (e.g., `.list-group-item-danger`). These modifier classes are built from the `$list-group-variants` map to make customizing the number and name of our modifier classes.

{{< scss-docs name="list-group-modifiers" file="scss/_list-group.scss" >}}

### CSS Vars
{{< css-vars-docs file="scss/_list-group.scss" >}}