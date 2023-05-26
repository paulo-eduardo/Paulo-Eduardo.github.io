<script lang="ts">
	const portifolio = [
		{
			title: "Coffee Cup",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Illustrator",
			tags: "Branding, Web Design",
			image: "coffee.jpg",
			url: "http://port1.com",
			modal: "#modal-01",
		},
		{
			title: "Console",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Web Design",
			tags: "Branding, Web Development",
			image: "console.jpg",
			url: "http://port2.com",
			modal: "#modal-02",
		},
		{
			title: "Judah",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Web Development",
			tags: "Branding, Web Programming",
			image: "judah.jpg",
			url: "http://port3.com",
			modal: "#modal-03",
		},
		{
			title: "Into The Light",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Photography",
			tags: "Photography, Design",
			image: "into-the-light.jpg",
			url: "http://port4.com",
			modal: "#modal-04",
		},
		{
			title: "Farmer Boy",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Branding",
			tags: "Branding, Web Design",
			image: "farmerboy.jpg",
			url: "http://port5.com",
			modal: "#modal-05",
		},
		{
			title: "Girl",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Photography",
			tags: "Photography, Graphic Design",
			image: "girl.jpg",
			url: "http://port6.com",
			modal: "#modal-06",
		},
		{
			title: "Origami",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Illustration",
			tags: "Branding, Illustration",
			image: "origami.jpg",
			url: "http://port7.com",
			modal: "#modal-07",
		},
		{
			title: "Retrocam",
			description:
				"Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			category: "Web Development",
			tags: "Photography",
			image: "retrocam.jpg",
			url: "http://port8.com",
			modal: "#modal-08",
		},
	];
</script>

<section id="portfolio">
	<div class="row">
		<div class="twelve columns collapsed">
			<h1>Check Out Some of My Works.</h1>
			<div id="portfolio-wrapper" class="bgrid-quarters s-bgrid-thirds cf">
				{#each portifolio as project (project.modal)}
					<div class="columns portfolio-item">
						<div class="item-wrap">
							<a href={project.modal} title="">
								<img alt="" src={"images/portfolio/" + project.image} />
								<div class="overlay">
									<div class="portfolio-item-meta">
										<h5>{project.title}</h5>
										<p>{project.category}</p>
									</div>
								</div>
							</a>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
