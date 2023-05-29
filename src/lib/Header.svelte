<script lang="ts">
	let navClass = "";

	let name = "Paulo Eduardo";
	let city = "Brazil";
	let occupation = "Back-end Developer";
	let description =
		"I architect and develop web services, ensuring constant optimization and improvement.";
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
					<a class="smothscroll" href="#home">{section}</a>
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
