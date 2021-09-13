---
title: IDBObjectStore.openKeyCursor()
slug: Web/API/IDBObjectStore/openKeyCursor
tags:
- API
- Database
- IDBObjectStore
- Method
- Reference
- Storage
- openKeyCursor
browser-compat: api.IDBObjectStore.openKeyCursor
---
<p>{{ APIRef("IndexedDB") }}</p>

<div>
  <p>The <strong><code>openKeyCursor()</code></strong> method of the
    {{domxref("IDBObjectStore")}} interface returns an {{domxref("IDBRequest")}} object
    whose result will be set to an {{domxref("IDBCursor")}} that can be used to iterate
    through matching results. Used for iterating through the keys of an object store with
    a cursor.</p>
</div>

<p>To determine if the add operation has completed successfully, listen for the
  results’s <code>success</code> event.</p>

<h2 id="Syntax">Syntax</h2>

<pre class="brush: js">var <em>request</em> = <em>objectStore</em>.openKeyCursor();
var <em>request</em> = <em>objectStore</em>.openKeyCursor(<em>query</em>);
var <em>request</em> = <em>objectStore</em>.openKeyCursor(<em>query</em>, <em>direction</em>);
</pre>

<h3 id="Parameters">Parameters</h3>

<dl>
  <dt><em>query </em>{{optional_inline}}</dt>
  <dd>The key range to be queried. If a single valid key is passed, this will default to a
    range containing only that key. If nothing is passed, this will default to a key range
    that selects all the records in this object store.</dd>
  <dt><em>direction </em>{{optional_inline}}</dt>
  <dd>An <a href="https://w3c.github.io/IndexedDB/#enumdef-idbcursordirection"><code>IDBCursorDirection</code></a> telling the cursor what direction to travel.
    Valid values are <code>"next"</code>, <code>"nextunique"</code>, <code>"prev"</code>,
    and <code>"prevunique"</code>. The default is <code>"next"</code>.</dd>
</dl>

<h3 id="Return_value">Return value</h3>

<p>An {{domxref("IDBRequest")}} object on which subsequent events related to this
  operation are fired.</p>

<h3 id="Exceptions">Exceptions</h3>

<p>This method may raise a {{domxref("DOMException")}} of one of the following types:</p>

<table class="standard-table">
  <thead>
    <tr>
      <th scope="col">Exception</th>
      <th scope="col">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>InvalidStateError</code></td>
      <td>This {{domxref("IDBObjectStore")}} or {{domxref("IDBIndex")}} has been deleted.
      </td>
    </tr>
    <tr>
      <td><code>TransactionInactiveError</code></td>
      <td>This {{domxref("IDBObjectStore")}}'s transaction is inactive.</td>
    </tr>
    <tr>
      <td><code>DataError</code></td>
      <td>The specified key or key range is invalid.<br>
         </td>
    </tr>
  </tbody>
</table>

<h2 id="Example">Example</h2>

<p>In this simple fragment we create a transaction, retrieve an object store, then use a
  cursor to iterate through all the records in the object store:</p>

<pre class="brush: js">var transaction = db.transaction("name", "readonly");
var objectStore = transaction.objectStore("name");
var request = objectStore.openKeyCursor();
request.onsuccess = function(event) {
  var cursor = event.target.result;
  if(cursor) {
    // cursor.key contains the key of the current record being iterated through
    // note that there is no cursor.value, unlike for openCursor
    // this is where you'd do something with the result
    cursor.continue();
  } else {
    // no more results
  }
};</pre>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="Browser_compatibility">Browser compatibility</h2>

<p>{{Compat}}</p>

<h2 id="See_also">See also</h2>

<ul>
  <li><a href="/en-US/docs/Web/API/IndexedDB_API/Using_IndexedDB">Using IndexedDB</a></li>
  <li>Starting transactions: {{domxref("IDBDatabase")}}</li>
  <li>Using transactions: {{domxref("IDBTransaction")}}</li>
  <li>Setting a range of keys: {{domxref("IDBKeyRange")}}</li>
  <li>Retrieving and making changes to your data: {{domxref("IDBObjectStore")}}</li>
  <li>Using cursors: {{domxref("IDBCursor")}}</li>
  <li>Reference example: <a class="external"
      href="https://github.com/mdn/to-do-notifications/tree/gh-pages">To-do
      Notifications</a> (<a class="external"
      href="https://mdn.github.io/to-do-notifications/">view example live</a>.)</li>
</ul>