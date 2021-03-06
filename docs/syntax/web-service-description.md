---
layout: default
title: Web service description
section: Syntax
permalink: /docs/syntax/web-service-description/
---

# Web service description format

All Origami web services are required to expose `/{version}/__about` endpoints to describe each version of the service.  The response give at this URL must be a JSON document conforming to the following format.

## Format

<table class="o-techdocs-table">
<tr>
	<th>Property</th>
	<th>Type</th>
	<th>Description</th>
</tr><tr>
	<td><code>{</code></td>
	<td></td>
	<td></td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>name</code></td>
	<td>string*</td>
	<td>The <b>repo</b> name of the web service</td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>apiVersion</code></td>
	<td>number*</td>
	<td>Integer version number of the API described by this document (ie. the version exposed in the URL path)</td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>appVersion</code></td>
	<td>string*</td>
	<td>Code version number (ie the version tag on the revision of the code that is checked out into this running instance)</td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>dateCreated</code></td>
	<td>string*</td>
	<td>ISO8601-format date when the app was first created</td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>support</code></td>
	<td>string*</td>
	<td>Copied from the matching property in the component's <a href="{{site.baseurl}}/docs/syntax/origamijson">origami.json</a> file.  For services that support all API versions in a single code version, it may be necessary to consult prior versions' origami.json files in order to find the appropriate value.</td>
</tr><tr>
	<td>&nbsp;&nbsp;<code>supportStatus</code></td>
	<td>string*</td>
	<td>Copied from the matching property in the component's <a href="{{site.baseurl}}/docs/syntax/origamijson">origami.json</a> file.  For services that support all API versions in a single code version, it may be necessary to consult prior versions' origami.json files in order to find the appropriate value.</td>
</tr><tr>
	<td><code>}</code></td>
	<td></td>
	<td></td>
</tr>
</table>

## Example


	{
	  "name": "tweet-service",
	  "apiVersion": 1,
	  "appVersion": "1.3.1",
	  "dateCreated": "2013-09-25T09:32:12+0200"
	  "support": "origamisupport-service-tweet@ft.com",
	  "supportStatus": "active",
	}
