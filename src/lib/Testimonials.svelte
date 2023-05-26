<script lang="ts">
	const testimonials = [
		{
			text: "Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			user: "John Doe",
		},
		{
			text: "Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit.",
			user: "Steve Smith",
		},
	];
</script>

<section id="testimonials">
	<div class="text-container">
		<div class="row">
			<div class="two columns header-col">
				<h1><span>Client Testimonials</span></h1>
			</div>
			<div class="ten columns flex-container">
				<ul class="slides">
					{#each testimonials as testimonial (testimonial.user)}
						<li>
							<blockquote>
								<p>{testimonial.text}</p>
								<cite>{testimonial.user}</cite>
							</blockquote>
						</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
</section>
