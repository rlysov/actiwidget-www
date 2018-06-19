---
title: 'Beautiful Widgets'
styles: app-widget-list
process:
    twig: true
    markdown: false
---

{% set carouselItems = [
	{ file: 'widget-bar-chart-dark.PNG', title: 'Bar chart (dark)' },
	{ file: 'widget-bar-chart-light.PNG', title: 'Bar chart (light)' },
	{ file: 'widget-card-dark.PNG', title: 'Card widget (dark)' },
	{ file: 'widget-card-light.PNG', title: 'Card widget (light)' },
	{ file: 'widget-custom-html-dark.PNG', title: 'Custom HTML widget (dark)' },
	{ file: 'widget-custom-html-light.PNG', title: 'Card widget (light)' },
	{ file: 'widget-donut-chart-dark.PNG', title: 'Donut Chart (dark)' },
	{ file: 'widget-line-chart-dark.PNG', title: 'Line Chart (dark)' },
	{ file: 'widget-list-view-dark.PNG', title: 'List View (dark)' },
	{ file: 'widget-plugin-dark.PNG', title: 'Your own widget as plugin' },
	{ file: 'widget-progress-circle-dark.PNG', title: 'Progress Circle (dark)' },
	{ file: 'widget-progress-circle-light.PNG', title: 'Progress Circle (light)' }
] 
%}


<div class="container">
	<div class="row text-center justify-content-center mb-5">
		<div class="col-8">
		  <h1>Beautiful widget pack</h1>
		</div>
	</div>
	
	<div class="row justify-content-center">
		<div class="col-4">
		  <p class="text-h3">
			Use build-in widgets to display your data. All widgets is optimized for mobile devices and tablets.
			<ul>
				<li>Card</li>
				<li>Bar chart</li>
				<li>Line chart</li>
				<li>Donut</li>
				<li>List view</li>
				<li>Progress circle</li>
				<li>Custom HTML widget</li>
			</ul>
			Or create your own widget with JavaScript\HTML using Plugins.
		  </p>
		</div>
		<div class="col-8">
			<div id="carousel1" class="carousel slide" data-ride="carousel">
				<div class="carousel-inner" style="height: 400px;">
								
				{% for item in carouselItems %}
					<div class="carousel-item text-center {% if loop.first %}active{% endif %}">
					  <img 
						class="d-block" 
						style="max-width: 100%; max-height: 100%; height: 300px;"
						src="{{page.media[item.file].url}}" alt="{{item.title}}">
						<div class="carousel-caption d-none d-md-block">
							<h3>{{item.title}}</h3>
							<p></p>
						</div>
					</div>
				{% endfor %}
	
				</div>
				<a class="carousel-control-prev" href="#carousel1" role="button" data-slide="prev">
					<span class="carousel-control-prev-icon" aria-hidden="true"></span>
					<span class="sr-only">Previous</span>
				</a>
				<a class="carousel-control-next" href="#carousel1" role="button" data-slide="next">
					<span class="carousel-control-next-icon" aria-hidden="true"></span>
					<span class="sr-only">Next</span>
				</a>
			</div>
		</div>
	</div>
</div>