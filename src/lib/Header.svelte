<script lang="ts">
	type Network = {
		name: string;
		url: string;
		className: string;
	};

	type PersonalData = {
		name: string;
		city: string;
		occupation: string;
		description: string;
		networks: Network[];
	};

	let name: string = "";
	let city: string = "";
	let occupation: string = "";
	let description: string = "";
	let networks: Array<Network> = [];

	fetch("me.json")
		.then((response) => response.json() as Promise<PersonalData>)
		.then((dataResponse) => {
			({ name, city, occupation, description, networks } = dataResponse);
		})
		.catch((error) => {
			console.error("Error:", error);
		});

	let navClass = "";
	let currentSection = "home";
	let sections = ["home", "about", "resume"];

	const checkSection = () => {
		const header = document.querySelector("header");
		const nav = document.getElementById("nav-wrap");

		if (header && nav) {
			let h = header.offsetHeight;
			let y = window.scrollY;

			if (y > h * 0.2 && y < h && window.outerWidth > 768) {
				nav.style.display = "none";
			} else {
				if (y < h * 0.2) {
					navClass = "";
					// nav.classList.remove("opaque");
					nav.style.display = "block";
				} else {
					// nav.classList.add("opaque");
					navClass = "opaque";
					nav.style.display = "block";
				}
			}
		}

		let scrollPosition = window.pageYOffset;

		sections.forEach((section) => {
			let sectionElement = document.getElementById(section);
			if (
				sectionElement.offsetTop <= scrollPosition &&
				sectionElement.offsetTop + sectionElement.offsetHeight > scrollPosition
			) {
				currentSection = section;
			}
		});
	};
</script>

<svelte:window on:scroll={checkSection} />

<header id="home">
	<nav id="nav-wrap" class={navClass}>
		<a class="mobile-btn" href="#nav-wrap" title="Show navigation"
			>Show navigation</a
		>
		<a class="mobile-btn" href="#top" title="Hide navigation">Hide Navigation</a
		>

		<ul id="nav" class="nav">
			{#each sections as section (section)}
				<li class={currentSection == section ? "current" : ""}>
					<a class="smothscroll" href="#{section}">{section}</a>
				</li>
			{/each}
		</ul>
	</nav>

	<div class="row banner">
		<div class="banner-text">
			<section id="home">
				<h1 class="responsive-headline">I'm {name}.</h1>
				<h3>I'm a {city} based <span>{occupation} </span> {description}</h3>
				<hr />
				<ul class="social">
					{#each networks as network (network.name)}
						<li>
							<a href={network.url} target="_blank"
								><i class={network.className} /></a
							>
						</li>
					{/each}
				</ul>
			</section>
		</div>
	</div>

	<p class="scrolldown">
		<a class="smoothscroll" href="#about"><i class="icon-down-circle" /></a>
	</p>
</header>
