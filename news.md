---
title: News
description: News
---
<div class="w3-responsive">
  <table class="w3-table-all w3-hoverable">
    <thead>
      <tr class="w3-teal">
        <th>#</th>
        <th>Title</th>
        <th>Date</th>
      </tr>
    </thead>
    <tbody style="cursor:pointer">
    {% for post in site.posts %}
      <tr onclick="window.location='{{ post.url }}'">
        <td><strong>{{ forloop.index }}</strong></td>
        <td>{{ post.title }}</td>
        <td>{{ post.date | truncatewords: 1, ""}}</td>
      </tr>
    {% endfor %}
    </tbody>
  </table>
</div>