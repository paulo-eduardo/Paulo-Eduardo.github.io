<script lang="ts">
	let networks = [
		// {
		// 	name: "facebook",
		// 	url: "http://facebook.com",
		// 	className: "fa fa-facebook",
		// },
		{
			name: "twitter",
			url: "https://twitter.com/pauloesdev",
			className: "fa fa-twitter",
		},
		// {
		// 	name: "google-plus",
		// 	url: "http://googleplus.com",
		// 	className: "fa fa-google-plus",
		// },
		{
			name: "linkedin",
			url: "https://www.linkedin.com/in/paulo-es/",
			className: "fa fa-linkedin",
		},
		{
			name: "instagram",
			url: "https://www.instagram.com/espaulo/",
			className: "fa fa-instagram",
		},
		{
			name: "github",
			url: "https://github.com/Paulo-Eduardo",
			className: "fa fa-github",
		},
		// {
		// 	name: "skype",
		// 	url: "http://skype.com",
		// 	className: "fa fa-skype",
		// },
	];
</script>

<footer>
	<div class="row">
		<div class="twelve columns">
			<ul class="social-links">
				{#each networks as network (network.name)}
					<li>
						<a href={network.url} target="_blank"
							><i class={network.className} /></a
						>
					</li>
				{/each}
			</ul>
			<ul class="copyright">
				<li>&copy; Copyright 2017 CeeVee</li>
			</ul>
		</div>
		<div id="go-top">
			<a class="smoothscroll" title="Back to Top" href="#home"
				><i class="icon-up-open" /></a
			>
		</div>
	</div>
</footer>
