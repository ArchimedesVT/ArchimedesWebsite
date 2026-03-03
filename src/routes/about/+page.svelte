<script>
	import Hero from '$lib/components/Hero.svelte';

	const teamConfig = {
		juvo: { label: 'Juvo', color: '#34d399' },
		astra: { label: 'Astra', color: '#60a5fa' },
		infinitum: { label: 'Infinitum', color: '#a78bfa' },
		terra: { label: 'Terra', color: '#fb923c' }
	};

	const groups = [
		{
			id: 'juvo',
			members: [
				{
					name: 'Abby Sobal',
					photo: '_DSC9350.JPG',
					bio: "I plan to major in mechanical engineering and am a member of Baja SAE, Astrobotics, and the Society of Hispanic Professional Engineers. I'm from Chilhowie, a one stoplight town in Southwest Virginia."
				},
				{
					name: 'Madison Kim',
					photo: '_DSC9345.JPG',
					bio: "Hi! My name is Madison and I am a Freshman planning to major in Mechanical Engineering. I am on Team Juvo and I work mostly on research and hardware. Outside of academics, I like playing volleyball and baking."
				},
				{
					name: 'Sabina Borjes',
					photo: '_DSC9339.JPG',
					bio: "Hi! I'm Sabina and I am a freshman majoring in Industrial Design and minoring in Human Computer Interaction. I love all things pink, sparkly, and cute!"
				},
				{
					name: 'Prehaan Parikh',
					photo: '_DSC9348.JPG',
					bio: "I'm an Industrial and Systems Engineering student passionate about creating meaningful impact through innovation, data-driven problem-solving, and social responsibility."
				},
				{
					name: 'Will Draper',
					photo: '_DSC9334.JPG',
					bio: "Hi! My name is Will, and I am a Mechanical Engineering student at Virginia Tech on Team Juvo. In my free time, I enjoy playing sports such as football and basketball."
				},
				{
					name: 'Ansh Khatiwada',
					photo: '_DSC9335.JPG',
					bio: "Hello everyone, my name is Ansh and I am a Computer Engineering major here at Virginia Tech. I am mainly responsible for the programming aspect of our project."
				},
				{
					name: 'Avril Yelland',
					photo: '_DSC9341.JPG',
					bio: "Hi I'm Avril and I am a freshman mechanical engineering major. I'm passionate about accessibility and how engineering can give that to people."
				}
			],
			advisors: [
				{
					name: 'Alexis Hamilton',
					photo: '',
					bio: "I am a sophomore in mechanical engineering, originally from Middletown, Delaware, and one of the advisors for the Juvo sub-team."
				},
				{
					name: 'Dianne Barahona Bonilla',
					photo: '',
					bio: "Dianne is a former member of JUVO, now serving as Advisor. She is a Mechanical Engineering major with a concentration in Robotics & Mechatronics."
				}
			]
		},
		{
			id: 'astra',
			members: [
				{
					name: 'Natalie Chapman',
					photo: 'natalie.png',
					bio: "I'm a freshman studying aerospace engineering from Pittsburgh, Pennsylvania. In addition to school I love to read and play music."
				},
				{
					name: 'Alena Arnold',
					photo: 'alena.png',
					bio: "Hi! I'm Alena! I'm a chemical engineering major on team Astra. I enjoy playing tennis!"
				},
				{
					name: 'Vamsi Sri Sai Guttikonda',
					photo: 'vamsi.png',
					bio: "Hello I'm Vamsi, I'm majoring in mechanical engineering and I'm a member of team Astra. I love to cook, lift, and listen to music in my free time."
				},
				{
					name: 'Aarya Gupta',
					photo: 'arya.png',
					bio: "Aarya is a Computer Engineering major who loves all things space. She can usually be spotted at Chipotle."
				},
				{
					name: 'Spencer Matijak',
					photo: 'spencer.png',
					bio: "Hello everyone, my name is Spencer and I am a first year electrical engineering student who hopes to one day work in microelectronics design."
				},
				{
					name: 'Logan Pepin',
					photo: 'logan.png',
					bio: "Hello, my name is Logan and I am on team ASTRA. I am a freshman here at Tech studying Mechanical engineering and applied music."
				},
				{
					name: 'Adam Younis',
					photo: 'adam.png',
					bio: "My name is Adam Younis, I like climbing, cooking and problem solving and I'm part of Archimedes' team Astra."
				}
			],
			advisors: [
				{
					name: 'Faith Pursley',
					photo: '',
					bio: "Hi! My name is Faith and I'm a sophomore studying Aerospace Engineering from Arizona. I was on the team last year as Project Manager."
				},
				{
					name: 'Evan Miller',
					photo: '',
					bio: "I am a sophomore Physics and Applied Math Major with a minor in nuclear engineering. In my free time I play music and stay active in sports and fitness."
				},
				{
					name: 'Aditeya Banerjee',
					photo: '',
					bio: "Aditeya is a sophomore in Mechanical Engineering and was part of Team Astra during his freshman year as Team Lead."
				}
			]
		},
		{
			id: 'infinitum',
			members: [
				{
					name: 'James Chandler Mercer',
					photo: '',
					bio: "Hey, I'm Chandler Mercer, I'm on the Infinitum team and have been programming web applications since I was 15."
				},
				{
					name: 'Rhea Parekh',
					photo: '',
					bio: "My name is Rhea Parekh and I am an ECE major at Tech! I love circuit-based hardware systems and building clean, user-friendly interfaces."
				},
				{
					name: 'Nicolas Parong',
					photo: '',
					bio: "I'm a Computer Engineering major who's very proud of his Filipino culture. Learning is truly a journey, and I'm glad to be in good company."
				},
				{
					name: 'Aleysa Marie Sweeney',
					photo: '',
					bio: "Freshman General Engineering major, planning to major in CS. I love doing nails and my own piercings!"
				},
				{
					name: 'Nira Marri',
					photo: '',
					bio: "Hi, I'm a freshman majoring in CS. I'm interested in programming, machine learning, and AI."
				},
				{
					name: 'Nikhita Kuninti',
					photo: '',
					bio: "I am a freshman majoring in computer science. I love math and coding. I also love dancing and cooking."
				}
			],
			advisors: [
				{
					name: 'Riva Jain',
					photo: '',
					bio: "Riva is one of the three 25-26 Infinitum advisors, focused primarily on machine learning work. She's a Computer Science major."
				},
				{
					name: 'Ameen Harandi',
					photo: '',
					bio: "Hi I'm Ameen, I'm a Computer Science student at Virginia Tech and I love to make products and small projects."
				},
				{
					name: 'Samhita Gupta',
					photo: '',
					bio: "I'm Samhita Gupta, a sophomore majoring in computer science and minoring in cybersecurity."
				}
			]
		},
		{
			id: 'terra',
			members: [
				{
					name: 'Andrew Friedman',
					photo: '_DSC9288.JPG',
					bio: "I have a passion for all things engineering and especially robotics. I like to spend my spare time playing video games or guitar."
				},
				{
					name: 'Dhruv Hassani',
					photo: '_DSC9313.JPG',
					bio: "I'm a freshman studying Electrical and Computer Engineering at Virginia Tech, originally from Phoenix, Arizona."
				},
				{
					name: 'Colin Gwon',
					photo: '_DSC9308.JPG',
					bio: "I'm a freshman at Virginia Tech majoring in ECE. I can be entertained with a good math problem and I am a big Pokémon fan."
				},
				{
					name: 'Kaeli Berry',
					photo: '_DSC9297.JPG',
					bio: "Hi! I'm Kaeli Berry, majoring in Mechanical Engineering and minoring in Industrial Design and Applied Voice. I love music and visual art."
				},
				{
					name: 'Parker Colasurdo',
					photo: '_DSC9306.JPG',
					bio: "I am a freshman majoring in Mechanical Engineering. My two favorite hobbies are video games and running."
				},
				{
					name: 'Kayla Scott',
					photo: '_DSC9310.JPG',
					bio: "I'm a freshman mechanical engineering major with an interest in automotive engineering. I love baking, cubing, and F1!"
				},
				{
					name: 'Anna Suh',
					photo: '_DSC9302.JPG',
					bio: "Hello! I am a freshman majoring in Computer Engineering and I am interested in Chip-Scale Integration. I like to hike, play games, and do art."
				},
				{
					name: 'Kai Bald',
					photo: '_DSC9292.JPG',
					bio: "I am a freshman electrical engineering major on Terra. I am interested in studying robotics and control systems."
				}
			],
			advisors: [
				{
					name: 'Gideon Lovern',
					photo: '',
					bio: "I'm a second year Electrical Engineering major and an advisor for Team Terra. I enjoy playing guitar, working out, hiking, and playing disc golf."
				}
			]
		}
	];

	function initials(name) {
		return name
			.split(' ')
			.filter(Boolean)
			.slice(0, 2)
			.map((n) => n[0].toUpperCase())
			.join('');
	}
</script>

<svelte:head>
	<title>About - Archimedes</title>
	<meta
		name="description"
		content="Learn about Archimedes at Virginia Tech and our mission to empower STEM freshmen."
	/>
</svelte:head>

<Hero title="About Archimedes" subtitle="Who we are" image="/images/hero-about.png" />

<section class="section">
	<div class="container">
		<div class="about-content">
			<div class="about-section">
				<h2>Who we are</h2>
				<p>
					Archimedes is an umbrella organization that encompasses four design teams, each
					participating in different national-level collegiate STEM competitions. The teams and their
					respective competitions are managed and operated by upperclassmen leads and guided by
					Virginia Tech professors and subject matter experts.
				</p>
			</div>

			<div class="about-section">
				<h2>Our mission</h2>
				<p>
					Archimedes was founded in 2015 on the principle that STEM freshmen are passionate,
					goal-driven problem solvers who are more than capable of conquering a design challenge. We
					strive to give freshmen a more in-depth experience than they might find in an
					upperclassmen-dominated team. Archimedes provides first-year STEM students with the tools,
					funding, and mentors to excel in their design competitions.
				</p>
			</div>
		</div>
	</div>
</section>

<section class="section members-section">
	<div class="container">
		<h2 class="members-title">Meet the teams</h2>

		{#each groups as group}
			<div class="team-group" style="--tc: {teamConfig[group.id].color}">
				<div class="team-header">
					<span class="team-pill">{teamConfig[group.id].label}</span>
					<div class="team-divider"></div>
				</div>

				<div class="members-grid">
					{#each group.members as member}
						<div class="member-card">
							<div class="member-photo">
								{#if member.photo}
									<img src="/members/{member.photo}" alt={member.name} />
								{:else}
									<span class="member-initials">{initials(member.name)}</span>
								{/if}
							</div>
							<div class="member-info">
								<p class="member-name">{member.name}</p>
								<p class="member-bio">{member.bio}</p>
							</div>
						</div>
					{/each}
				</div>

				{#if group.advisors.length}
					<div class="advisors-row">
						<p class="advisors-label">Advisors</p>
						<div class="advisors-grid">
							{#each group.advisors as advisor}
								<div class="advisor-card">
									<div class="advisor-avatar">
										{#if advisor.photo}
											<img src="/members/{advisor.photo}" alt={advisor.name} />
										{:else}
											<span class="member-initials advisor-initials"
												>{initials(advisor.name)}</span
											>
										{/if}
									</div>
									<div class="advisor-info">
										<p class="member-name">{advisor.name}</p>
										<p class="member-bio">{advisor.bio}</p>
									</div>
								</div>
							{/each}
						</div>
					</div>
				{/if}
			</div>
		{/each}
	</div>
</section>

<style>
	.about-content {
		max-width: 900px;
		margin: 0 auto;
	}

	.about-section {
		margin-bottom: 4rem;
	}

	.about-section h2 {
		color: var(--archimedes-yellow);
		margin-bottom: 1.5rem;
		text-align: center;
	}

	.about-section > p {
		font-size: 1.1rem;
		line-height: 1.8;
		text-align: center;
	}

	/* Members section */
	.members-section {
		padding-top: 0;
	}

	.members-title {
		text-align: center;
		color: var(--archimedes-yellow);
		margin-bottom: 4rem;
	}

	/* Team group */
	.team-group {
		margin-bottom: 5rem;
	}

	.team-header {
		display: flex;
		align-items: center;
		gap: 1.25rem;
		margin-bottom: 2rem;
	}

	.team-pill {
		flex-shrink: 0;
		font-size: 0.8rem;
		font-weight: 800;
		text-transform: uppercase;
		letter-spacing: 0.14em;
		color: var(--tc);
		border: 2px solid var(--tc);
		border-radius: 999px;
		padding: 0.3rem 1rem;
	}

	.team-divider {
		flex: 1;
		height: 1px;
		background: linear-gradient(to right, var(--tc), transparent);
		opacity: 0.35;
	}

	/* Member cards grid */
	.members-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(190px, 1fr));
		gap: 1.25rem;
	}

	.member-card {
		background: rgba(255, 255, 255, 0.04);
		border: 1px solid rgba(255, 255, 255, 0.07);
		border-top: 3px solid var(--tc);
		border-radius: var(--radius-lg);
		overflow: hidden;
		display: flex;
		flex-direction: column;
		transition:
			transform var(--tr),
			background var(--tr);
	}

	.member-card:hover {
		transform: translateY(-4px);
		background: rgba(255, 255, 255, 0.07);
	}

	.member-photo {
		width: 100%;
		aspect-ratio: 1;
		background: rgba(255, 255, 255, 0.06);
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}

	.member-photo img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.member-initials {
		font-size: 2rem;
		font-weight: 800;
		color: var(--tc);
		letter-spacing: 1px;
	}

	.member-info {
		padding: 1rem;
		display: flex;
		flex-direction: column;
		gap: 0.4rem;
		flex: 1;
	}

	.member-name {
		font-weight: 700;
		font-size: 0.95rem;
		color: var(--text-on-dark);
		margin: 0;
	}

	.member-bio {
		font-size: 0.8rem;
		line-height: 1.55;
		color: rgba(255, 252, 242, 0.6);
		margin: 0;
		display: -webkit-box;
		-webkit-line-clamp: 3;
		-webkit-box-orient: vertical;
		overflow: hidden;
	}

	/* Advisors */
	.advisors-row {
		margin-top: 1.5rem;
	}

	.advisors-label {
		font-size: 0.72rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 0.14em;
		color: rgba(255, 252, 242, 0.4);
		margin-bottom: 0.75rem;
	}

	.advisors-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
		gap: 0.75rem;
	}

	.advisor-card {
		background: rgba(255, 255, 255, 0.025);
		border: 1px solid rgba(255, 255, 255, 0.06);
		border-left: 3px solid var(--tc);
		border-radius: var(--radius-md);
		padding: 0.85rem 1rem;
		display: flex;
		align-items: flex-start;
		gap: 0.85rem;
	}

	.advisor-avatar {
		width: 48px;
		height: 48px;
		border-radius: 50%;
		background: rgba(255, 255, 255, 0.08);
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
		flex-shrink: 0;
	}

	.advisor-avatar img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.advisor-initials {
		font-size: 1rem;
	}

	.advisor-info {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
		min-width: 0;
	}

	.advisor-info .member-name {
		font-size: 0.9rem;
	}

	.advisor-info .member-bio {
		-webkit-line-clamp: 2;
	}

	@media (max-width: 768px) {
		.members-grid {
			grid-template-columns: repeat(2, 1fr);
			gap: 0.85rem;
		}

		.advisors-grid {
			grid-template-columns: 1fr;
		}

		.member-initials {
			font-size: 1.5rem;
		}
	}

	@media (max-width: 480px) {
		.members-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
