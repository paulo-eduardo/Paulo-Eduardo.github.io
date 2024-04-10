<script lang="ts">
	type Address = {
		country: string;
		state: string;
	};

	type Data = {
		name: string;
		image: string;
		bio: string;
		email: string;
		phone: string;
		address: Address;
		resumeDownload: string;
	};

	let data: Data;
	let name: string;
	let image: string;
	let bio: string;
	let email: string;
	let phone: string;
	let resumeDownload: string;
	let state: string;
	let country: string;

	fetch("me.json")
		.then((response) => response.json() as Promise<Data>)
		.then((dataResponse) => {
			data = dataResponse;
			({ name, image, bio, email, phone, resumeDownload } = data);
			({ state, country } = data.address);
		})
		.catch((error) => {
			console.error("Error:", error);
		});
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
						<span> {state} - {country} </span>
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
