<script lang="ts">
	type Network = {
		name: string;
		url: string;
		className: string;
	};

	let networks: Array<Network> = [];

	fetch("me.json")
		.then((response) => response.json())
		.then((dataResponse) => {
			({ networks } = dataResponse);
		})
		.catch((error) => {
			console.error("Error:", error);
		});
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
