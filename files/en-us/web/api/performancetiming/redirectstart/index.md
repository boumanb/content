---
title: PerformanceTiming.redirectStart
slug: Web/API/PerformanceTiming/redirectStart
tags:
- API
- Backwards compatibility
- Deprecated
- Navigation Timing
- PerformanceTiming
- Property
- Read-only
- Reference
- legacy
browser-compat: api.PerformanceTiming.redirectStart
---
<p>{{APIRef("Navigation Timing")}}{{Deprecated_Header}}</p>

<div class="notecard warning">
  <p><strong>Warning:</strong> This interface of this property is deprecated in the <a href="https://w3c.github.io/navigation-timing/#obsolete">Navigation Timing Level 2 specification</a>. Please use the {{domxref("PerformanceNavigationTiming")}}
    interface instead.</p>
</div>

<p>The legacy
  <strong><code>PerformanceTiming.redirectStart</code></strong>
  read-only property returns an <code>unsigned long long</code> representing the moment,
  in milliseconds since the UNIX epoch, the first HTTP redirect starts. If there is no
  redirect, or if one of the redirect is not of the same origin, the value returned is
  <code>0</code>.</p>

<h2 id="Syntax">Syntax</h2>

<pre
  class="brush: js"><em>time</em> = <em>performanceTiming</em>.redirectStart;</pre>

<h2 id="Specifications">Specifications</h2>

<p>This feature is no longer on track to become a standard, as the <a href="https://w3c.github.io/navigation-timing/#obsolete">Navigation Timing specification</a> has marked it as deprecated.
  Use the {{domxref("PerformanceNavigationTiming")}} interface instead.</p>

<h2 id="Browser_compatibility">Browser compatibility</h2>

<p>{{Compat}}</p>

<h2 id="See_also">See also</h2>

<ul>
  <li>The {{domxref("PerformanceTiming")}} interface it belongs to.</li>
</ul>