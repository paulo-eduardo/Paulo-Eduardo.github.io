<script lang="ts">
	let data = {
		// education: [
		// 	{
		// 		school: "University of Tech",
		// 		degree: "Master in JavaScript",
		// 		graduated: "April 2017",
		// 		description:
		// 			"Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. Nullam dictum felis eu pede mollis pretium.",
		// 	},
		// 	{
		// 		school: "School of Developers",
		// 		degree: "B.A. Degree in Graphic Design",
		// 		graduated: "March 2013",
		// 		description:
		// 			"This is Photoshops version of Lorem Ipsum. Proin gravida nibh vel velit auctor aliquet. Aenean sollicitudin, lorem quis bibendum auctor, nisi elit consequat ipsum, nec sagittis sem nibh id elit. Duis sed odio sit amet nibh vulputate cursus a sit amet mauris. Morbi accumsan ipsum velit. Nam nec tellus a odio tincidunt auctor a ornare odio. Sed non mauris vitae erat",
		// 	},
		// ],
		work: [
			{
				company: "X-Team",
				title: "Software Engineer",
				years: "Apr 2021 - June 2022",
				description: `Software Engineer responsible for development, maintenance and upgrades of the following projects\n
                      Beachbody’s:
                      • Mainly responsible for Front-End engineering using React, Styled Components, and Storybooks
                      building several features;
                      • Creating a proxy component between distinct types of video with rating modal;
                      • Implemented a feature to redirect users to a promotional page from a shareable link;
                      • All Unit tests have been written in React Testing Library, also fixing bugs;
                      • Using GraphQL to consume Web APIs.
                      • Also supported upgrades and maintenance to beachbodyondeman.com\n
                      X-Team’s:
                      Backing the internal platforms (XHQ and the XP Jobs) doing maintenance and upgrades focused on Full Stack services.\n
                      Tech stack: Node.js, TypeScript, Docker, React, Gatsby, Styled Components, Storybooks, React Testing Library, Jest, Slack.`,
			},
			{
				company: "ClubPetro",
				title: "Javascript Software Engineer",
				years: "Apr 2020 - Fev 2021",
				description: `Oversaw a customer loyalty application for a business solution focused on gas stations.\n
                    • Developed Microservice architecture, including RESTful API using Node.js, Nest.js, TypeScript; • Built an interface to manage the customers' loyalty program by adding new features
                    and improved performance in React and TypeScript;
                    • Created Monorepo for CloudFunctions (GCP) in Nest.js, also using WebPack to
                    build individual deployable files;
                    • All the Unit Tests have been written in Jest;
                    • The development environment was configured inside a Docker container.\n
                    Tech stack: Node.js, Nest.js, Docker, GCP, TypeScript, React, Webpack, PostgreSQL.`,
			},
			{
				company: "Lyncas",
				title: "Full Stack Javascript Developer",
				years: "May 2019 - Mar 2020",
				description: `Engaged in several web-related applications designed for planning and controlling the entire production stage from one of the biggest textile companies based in Brazil.
                      The Web API was created for reducing the time plotting from a week to less than three business days, therefore upscaling their profit/sales.\n
                      • Enhanced and shaped microservice architecture RESTful API with Node.js and Express; • Designed a web interface in React.js to manage and request the exact number of items produced whilst supervising the production stages;
                      • The entire development environment was configured inside a Docker container.\n
                      Tech stack: Node.js, Express, MongoDB, Docker.`,
			},
			{
				company: "Freelance",
				title: "Software Engineer",
				years: "2010 - 2019",
				description: `From 2010 to 2019 I worked on a great variety of projects, such as:
                      • Deeper Systems: Worked on board gaming platform for a Portuguese Enterprise. Oversaw Full
                      Stack development tasks by using Python and Vue.js. Enhanced and shaped microservice architecture RESTful API, built an interface to play Pasur (card game) using Vue.js and also developed an interface to watch a chess game, where the player was able to review every single command he performed during match;
                      • Icetech: Developed mobile apps using Ionic and Angular;
                      • Benner: evolved the web development from the company in C# and also proprietary tools;
                      • Inventti: In charge of create an ERP (further called MYRP) in C#;
                      • Operacional Solution OS: Developed a Gantt in Windows Form application in C#;
                      • T-Systems do Brasil: Responsible for the development of a web application in C#;\n
                      Tech stack: C#, Python, Django, Pyramid, Vue.js, Docker, MongoDB, PL/SQL, MySQL.`,
			},
		],
		skills: [
			{
				name: "Language",
				items: ["Javascript", "TypeScript", "Go", "Python", "C#"],
			},
			{
				name: "Frameworks",
				items: ["Express.js", "Gin", "Mux", "Hapi.js"],
			},
			{
				name: "Tools",
				items: ["Bash", "Git & Github", "Postman", "MongoDB"],
			},
		],
	};

	const { work, skills } = data;
</script>

<section id="resume">
	<div class="row skill">
		<div class="three columns header-col">
			<h1><span>Skills</span></h1>
		</div>
		<div class="nine columns main-col">
			<p>
				My main specialties include Go, JS / Typescript, Node.js, Express,
				Serverless, React, Redux, AWS, Docker, Vue.js and RESTful API. I am
				passionate about back-end development and that is what I am most focused
				on, but I really like React.js when it comes to front-end development. I
				am also committed to staying up-to-date with the latest technologies and
				have been learning GoLang for a time now and going in-depth with DevOps
				culture.
			</p>

			<div class="skills row">
				{#each skills as skill (skill.name)}
					<div class="skills columns">
						<h4>{skill.name}</h4>
						<ul>
							{#each skill.items as item (item)}
								<li>{item}</li>
							{/each}
						</ul>
					</div>
				{/each}
			</div>
		</div>
		<!-- TODO: add education and position it after work -->
		<!-- <div class="row education">
		<div class="three columns header-col">
			<h1><span>Education</span></h1>
			<br />
		</div>
		{education}
	</div> -->
		<div class="row work">
			<div class="three columns header-col">
				<h1><span>Work</span></h1>
				<br />
			</div>
			{#each work as job (job.company)}
				<div class="row item">
					<div class="twelve columns">
						<h3>{job.company}</h3>
						<p class="info">
							{job.title}<span>&bull;</span> <em class="date">{job.years}</em>
						</p>

						<p>
							{@html job.description.replace(/\n/g, "<br />")}
						</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
