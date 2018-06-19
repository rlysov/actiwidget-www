---
title: 'Usage example'
process:
    twig: true
    markdown: false
---

<div class="container">
      <div class="row text-center">
        <div class="col-12">
          <h1>Usage example</h1>
          <p class="text-h3"><em>create simple bitcoin price dashboard in minutes</em></p>
        </div>
      </div>

      <div class="row pt-3 pt-xl-5">
        <div class="col-12 col-sm-10 m-auto m-md-0 col-md-8">
			<p class="text-h3">
			1. Describe dashboard structure in 
			<a href="{{ page.canonical() }}/example.json" target="_blank">JSON file</a> 
			and host it at any server (ex. <a target="_blank" href="http://myjson.com/">http://myjson.com/</a>)
			</p>
			<div class="json-viewer-container"><pre id="json-viewer"></pre></div>
        </div>

        <div class="col-12 col-sm-10 m-auto m-md-0 col-md-4 pt-5 pt-md-0">
			<p class="text-h3">2. Add json url to mobile app and open your dashboard</p>
			<img alt="image" class="img-fluid" src="{{ page.canonical() }}/example1-phone.png">
        </div>
      </div>
</div>

<script>
    $(document).ready(function(){
        $.get("{{ page.canonical() }}/example.json", function(json){
       		$("#json-viewer").jsonViewer(json, {collapsed: false, collapseLevel: 4, withQuotes: true});
      	});
    });
</script>
    