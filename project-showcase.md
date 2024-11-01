---
layout: page
title: "Project Showcase"
permalink: /project-showcase/
---
# Project Showcase
Here installers can share their completed projects, and customers can leave their feedback.
{% for project in site.projects %}
## {{ project.title }}
Installer: {{ project.installer }}
Date: {{ project.date | date: "%B %d, %Y" }}
{{ project.content }}
{% endfor %}
<div id="disqus_thread"></div>
<script>
var disqus_config = function () {
    this.page.url = "{{ page.url }}"; 
    this.page.identifier = "{{ page.title }}";
};
(function() {
    var d = document, s = d.createElement('script');
    s.src = 'https-donald-desing-github-io-friendly-guacamole';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the comments.</noscript>
<h3>Comments</h3>
<div id="comments"></div>
<form id="commentForm">
    <label for="commentText">Leave a comment:</label>
    <textarea id="commentText" required></textarea>
    <button type="submit">Post Comment</button>
</form>

<script>
    document.getElementById('commentForm').onsubmit = function(event) {
        event.preventDefault();
        const comment = document.getElementById('commentText').value;
        const commentDiv = document.createElement('div');
        commentDiv.innerHTML = <p>${comment}</p>;
        document.getElementById('comments').appendChild(commentDiv);
        this.reset();
    };
</script>
