<script lang="ts">
	type Work = {
		company: string;
		title: string;
		years: string;
		description: string[];
	};

	type Skill = {
		name: string;
		items: string[];
	};

	type Data = {
		work: Work[];
		skills: Skill[];
		skills_text: string;
	};

	let work: Work[] = [];
	let skills: Skill[] = [];
	let skills_text: string;

	fetch("work.json")
		.then((response) => response.json() as Promise<Data>)
		.then((data) => {
			work = data.work;
			skills = data.skills;
			skills_text = data.skills_text;
		})
		.catch((error) => {
			console.error("Error:", error);
		});
</script>

<section id="resume">
	<div class="row skill">
		<div class="three columns header-col">
			<h1><span>Skills</span></h1>
		</div>
		<div class="nine columns main-col">
			<p>
				{skills_text}
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
							{#each job.description as description}
								{@html description.replace(/\n/g, "<br />")}
								<br />
							{/each}
						</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
