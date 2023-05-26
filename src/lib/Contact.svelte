<section id="contact">
	<div class="row section-head">
		<div class="two columns header-col">
			<h1><span>Get In Touch.</span></h1>
		</div>
		<div class="ten columns">
			<p class="lead">
				Sed ut perspiciatis unde omnis iste natus error sit voluptatem
				accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab
				illo inventore veritatis et quasi architecto beatae vitae dicta sunt
				explicabo. Nemo enim ipsam voluptatem quia aut odit aut fugit.
			</p>
		</div>
		<!-- <div class="">
			<a
				href="mailto:example@example.com?subject=Email%20Subject&body=Body%20Text"
				class="submit">Send me a Email</a
			>
		</div>
	</div> -->
		<div class="row">
			<div class="eight columns">
				<form action="" method="post" id="contactForm" name="contactForm">
					<fieldset>
						<div>
							<label htmlFor="contactName"
								>Name <span class="required">*</span></label
							>
							<input
								type="text"
								value=""
								size="35"
								id="contactName"
								name="contactName"
							/>
						</div>
						<div>
							<label htmlFor="contactEmail"
								>Email <span class="required">*</span></label
							>
							<input
								type="text"
								value=""
								size="35"
								id="contactEmail"
								name="contactEmail"
							/>
						</div>
						<div>
							<label htmlFor="contactSubject">Subject</label>
							<input
								type="text"
								value=""
								size="35"
								id="contactSubject"
								name="contactSubject"
							/>
						</div>
						<div>
							<label htmlFor="contactMessage"
								>Message <span class="required">*</span></label
							>
							<textarea
								cols="50"
								rows="15"
								id="contactMessage"
								name="contactMessage"
							/>
						</div>
						<div>
							<button class="submit">Submit</button>
							<span id="image-loader">
								<img alt="" src="images/loader.gif" />
							</span>
						</div>
					</fieldset>
				</form>
				<div id="message-warning">Error boy</div>
				<div id="message-success">
					<i class="fa fa-check" />Your message was sent, thank you!<br />
				</div>
			</div>
		</div>
	</div>
</section>
