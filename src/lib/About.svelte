<script lang="ts">
	let data = {
		name: "Paulo Eduardo da Silva",
		image: "images/profilepic.jpg",
		bio: "Hi, I’m a problem solver and I love to face new challenges! A senior developer with twelve years of career who loves to learn and evolve. Recently I’ve worked on one of the biggest international remote companies as a full stack developer and now I am focused on migrating to backend development.",
		email: "pauloes.dev@gmail.com",
		phone: "+55 (47) 93618-0910",
		address: {
			street: "Aracaju - Centro",
			city: "Timbó",
			state: "SC",
			zip: "89120-000",
		},
		resumeDownload:
			"https://docs.google.com/document/d/1LANNHRSDkEUWxLinm91SpZv-vqeD6wc2YaT_IGy6OmY/export?format=pdf",
	};
	const { name, image, bio, email, phone, resumeDownload } = data;
	const { street, city, state, zip } = data.address;
</script>

<section id="about">
	<div class="row">
		<div class="three columns">
			<img class="profile-pic" src={image} alt="" />
		</div>
		<div class="nine columns main-col">
			<h2>About Me</h2>
			<p>{bio}</p>
			<div class="row">
				<div class="columns contact-details">
					<h2>Contact Details</h2>
					<p class="address">
						<span>{name}</span><br />
						<span>
							{street}<br />
							{city}, {state}
							{zip}
						</span>
						<br />
						<span>{phone}</span><br />
						<a href="mailto:{email}" class="email">{email}</a>
					</p>
				</div>
				<div class="columns download">
					<p>
						<a href={resumeDownload} class="button"
							><i class="fa fa-download" />Download Resume</a
						>
					</p>
				</div>
			</div>
		</div>
	</div>
</section>
