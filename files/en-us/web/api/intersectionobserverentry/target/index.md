---
title: IntersectionObserverEntry.target
slug: Web/API/IntersectionObserverEntry/target
tags:
- API
- Element
- Experimental
- Intersection Observer
- Intersection Observer API
- IntersectionObserver
- Property
- Reference
- target
browser-compat: api.IntersectionObserverEntry.target
---
<div>{{APIRef("Intersection Observer API")}}{{SeeCompatTable}}</div>

<p>The {{domxref("IntersectionObserverEntry")}} interface's
    read-only <strong><code>target</code></strong> property indicates which targeted
    {{domxref("Element")}} has changed its amount of intersection with the intersection
    root.</p>

<h2 id="Syntax">Syntax</h2>

<pre class="brush: js"><var><code>var <em>target</em> = </code>IntersectionObserverEntry</var>.target;
</pre>

<h3 id="Value">Value</h3>

<p>The <code>IntersectionObserverEntry</code>'s <code>target</code> property specifies
  which {{domxref("Element")}} previously targeted by calling
  {{domxref("IntersectionObserver.observe()")}} experienced a change in intersection with
  the root.</p>

<h2 id="Example">Example</h2>

<p>In this simple example, each targeted element's {{cssxref("opacity")}} is set to its
  {{domxref("IntersectionObserverEntry.intersectionRatio", "intersectionRatio")}}.</p>

<pre class="brush: js">function intersectionCallback(entries) {
  entries.forEach(function(entry) {
    entry.target.opacity = entry.intersectionRatio;
  });
}</pre>

<p>To see a more concrete example, take a look at
  {{SectionOnPage("/en-US/docs/Web/API/Intersection_Observer_API/Timing_element_visibility",
  "Handling intersection changes")}}.</p>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="Browser_compatibility">Browser compatibility</h2>

<p>{{Compat}}</p>