<script>
	import { browser } from '$app/environment';
	import { fade } from 'svelte/transition';
	import Hero from '$lib/components/Hero.svelte';

	const officers = [
		{ role: 'President', name: 'Nidhi Gangadharan', image: '' },
		{ role: 'VP', name: 'Indu Sanil', image: '' },
		{ role: 'Secretary', name: 'Sophie Atkisson', image: '' },
		{ role: 'External Treasurer', name: 'Xander Fry', image: '' },
		{ role: 'External Treasurer', name: 'Kevin Xu', image: '' },
		{ role: 'Internal Treasurer', name: 'Helen Brown', image: '' },
		{ role: 'Recruitment/Publicity', name: 'Bella Guereca', image: '' },
		{ role: 'External Relations', name: 'Ramsey Wondersek', image: '' },
		{ role: 'Webmaster', name: 'Owen Stuckman', image: '' }
	];

	const teamConfig = {
		juvo: { label: 'Juvo', color: '#34d399' },
		astra: { label: 'Astra', color: '#60a5fa' },
		infinitum: { label: 'Infinitum', color: '#a78bfa' },
		terra: { label: 'Terra', color: '#fb923c' }
	};

	/**
	 * @param {string} driveUrl
	 * @returns {string}
	 */
	function driveImg(driveUrl) {
		if (!driveUrl) return '';
		const m = driveUrl.match(/\/d\/([^/]+)/);
		return m ? `https://drive.google.com/thumbnail?id=${m[1]}&sz=w800` : '';
	}

	const groups = [
		{
			id: /** @type {'juvo'} */ ('juvo'),
			members: [
				{
					name: 'Abby Sobal',
					photo: driveImg('https://drive.google.com/file/d/1U4H5w1vuGunMndxVLIccMt-M-s62bGb4/view?usp=sharing'),
					bio: "I plan to major in mechanical engineering and am a member of Baja SAE, Astrobotics, and the Society of Hispanic Professional Engineers. I'm from Chilhowie, a one stoplight town in Southwest Virginia."
				},
				{
					name: 'Madison Kim',
					photo: driveImg('https://drive.google.com/file/d/1eW1Wc-1Pra2zh7-kusMr897PimFE6QrK/view?usp=sharing'),
					bio: "Hi! My name is Madison and I am a Freshman planning to major in Mechanical Engineering. I am on Team Juvo and I work mostly on research and hardware. Outside of academics, I like playing volleyball and baking."
				},
				{
					name: 'Sabina Borjes',
					photo: driveImg('https://drive.google.com/file/d/1cdZad1fSSAqjDNhyBhNnGWWObegS52mh/view?usp=sharing'),
					bio: "Hi! I'm Sabina and I am a freshman majoring in Industrial Design and minoring in Human Computer Interaction. I love all things pink, sparkly, and cute!"
				},
				{
					name: 'Prehaan Parikh',
					photo: driveImg('https://drive.google.com/file/d/1kKHkHs9NT0M4Qm6QPYXvdvagyag7oE1o/view?usp=sharing'),
					bio: "I'm an Industrial and Systems Engineering student passionate about creating meaningful impact through innovation, data-driven problem-solving, and social responsibility."
				},
				{
					name: 'Will Draper',
					photo: driveImg('https://drive.google.com/file/d/1c4jSpBcHivd43sOgcz5BBK1UbsMD3pk8/view?usp=sharing'),
					bio: "Hi! My name is Will, and I am a Mechanical Engineering student at Virginia Tech on Team Juvo. In my free time, I enjoy playing sports such as football and basketball."
				},
				{
					name: 'Ansh Khatiwada',
					photo: driveImg('https://drive.google.com/file/d/1u3GhECEhvg6amzhSjPDGJSJSFO6wNFMJ/view?usp=sharing'),
					bio: "Hello everyone, my name is Ansh and I am a Computer Engineering major here at Virginia Tech. I am mainly responsible for the programming aspect of our project."
				},
				{
					name: 'Avril Yelland',
					photo: driveImg('https://drive.google.com/file/d/1cl_hbN39cS1KSD78RJ5icCijWyCpxbTq/view?usp=sharing'),
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
			id: /** @type {'astra'} */ ('astra'),
			members: [
				{
					name: 'Natalie Chapman',
					photo: driveImg('https://drive.google.com/file/d/1MzApLmVFb8T4RVbQVLRYi22PqF6fNjb-/view?usp=sharing'),
					bio: "I'm a freshman studying aerospace engineering from Pittsburgh, Pennsylvania. In addition to school I love to read and play music."
				},
				{
					name: 'Alena Arnold',
					photo: driveImg('https://drive.google.com/file/d/1S6mCgyvOZ3cvbMiN12yYuGKjorUGXV8S/view?usp=sharing'),
					bio: "Hi! I'm Alena! I'm a chemical engineering major on team Astra. I enjoy playing tennis!"
				},
				{
					name: 'Vamsi Sri Sai Guttikonda',
					photo: driveImg('https://drive.google.com/file/d/1-5puDfSMnq1ic_Et6hivB4UbFsiD60q4/view?usp=sharing'),
					bio: "Hello I'm Vamsi, I'm majoring in mechanical engineering and I'm a member of team Astra. I love to cook, lift, and listen to music in my free time."
				},
				{
					name: 'Aarya Gupta',
					photo: driveImg('https://drive.google.com/file/d/1XkGfZnK-u8_jszYy_j1SvQ5noeF76k2O/view?usp=sharing'),
					bio: "Aarya is a Computer Engineering major who loves all things space. She can usually be spotted at Chipotle."
				},
				{
					name: 'Spencer Matijak',
					photo: driveImg('https://drive.google.com/file/d/18oJuONr3s5Bg-RH3KCpDRgSnAf8NR-EQ/view?usp=sharing'),
					bio: "Hello everyone, my name is Spencer and I am a first year electrical engineering student who hopes to one day work in microelectronics design."
				},
				{
					name: 'Logan Pepin',
					photo: driveImg('https://drive.google.com/file/d/1IMrl5k7D53WBZMpY15F_GR-VfdDFzl2Q/view?usp=sharing'),
					bio: "Hello, my name is Logan and I am on team ASTRA. I am a freshman here at Tech studying Mechanical engineering and applied music."
				},
				{
					name: 'Adam Younis',
					photo: driveImg('https://drive.google.com/file/d/1lb0w0cMFACDd4vEIX0jIQCAfMSgdGZPu/view?usp=sharing'),
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
			id: /** @type {'infinitum'} */ ('infinitum'),
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
			id: /** @type {'terra'} */ ('terra'),
			members: [
				{
					name: 'Andrew Friedman',
					photo: driveImg('https://drive.google.com/file/d/1PzcbMCPo1uutVtXtGTwzrIb8zHnShILD/view?usp=sharing'),
					bio: "I have a passion for all things engineering and especially robotics. I like to spend my spare time playing video games or guitar."
				},
				{
					name: 'Dhruv Hassani',
					photo: driveImg('https://drive.google.com/file/d/1HNpk-IQV2riiJds41ciPd2S1PDNpqJPx/view?usp=sharing'),
					bio: "I'm a freshman studying Electrical and Computer Engineering at Virginia Tech, originally from Phoenix, Arizona."
				},
				{
					name: 'Colin Gwon',
					photo: driveImg('https://drive.google.com/file/d/1hw25ldLIeLBgnlMB1VC7cBHLJVG2Dv0k/view?usp=sharing'),
					bio: "I'm a freshman at Virginia Tech majoring in ECE. I can be entertained with a good math problem and I am a big Pokémon fan."
				},
				{
					name: 'Kaeli Berry',
					photo: driveImg('https://drive.google.com/file/d/1eI3zd_StnLSvwJgU9WJL9g43GOCQUxCC/view?usp=sharing'),
					bio: "Hi! I'm Kaeli Berry, majoring in Mechanical Engineering and minoring in Industrial Design and Applied Voice. I love music and visual art."
				},
				{
					name: 'Parker Colasurdo',
					photo: driveImg('https://drive.google.com/file/d/1bgt9DgFYC3S3hWjpTn8g3cJGR3ivpjby/view?usp=sharing'),
					bio: "I am a freshman majoring in Mechanical Engineering. My two favorite hobbies are video games and running."
				},
				{
					name: 'Kayla Scott',
					photo: driveImg('https://drive.google.com/file/d/1TMoCclDcVJGABtP6jaPu472rZNLaEv2h/view?usp=sharing'),
					bio: "I'm a freshman mechanical engineering major with an interest in automotive engineering. I love baking, cubing, and F1!"
				},
				{
					name: 'Anna Suh',
					photo: driveImg('https://drive.google.com/file/d/1a9Lboy6976cgucz6BaUOhUVEN9TL296k/view?usp=sharing'),
					bio: "Hello! I am a freshman majoring in Computer Engineering and I am interested in Chip-Scale Integration. I like to hike, play games, and do art."
				},
				{
					name: 'Kai Bald',
					photo: driveImg('https://drive.google.com/file/d/1jwat-6yTxCTPwQajBR4V2kjmu1n6yyAr/view?usp=sharing'),
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

	/** @param {string} name */
	function initials(name) {
		return name
			.split(' ')
			.filter(Boolean)
			.slice(0, 2)
			.map((n) => n[0].toUpperCase())
			.join('');
	}

	/* ── Overlay state ── */
	/** @type {typeof groups[number] | null} */
	let overlayGroup = null;
	let overlayIndex = 0;
	/** @type {HTMLDivElement | undefined} */
	let scrollContainer;

	/** @param {typeof groups[number]} group */
	function getAllMembers(group) {
		return [
			...group.members.map((m) => ({ ...m, isAdvisor: false })),
			...group.advisors.map((a) => ({ ...a, isAdvisor: true }))
		];
	}

	/**
	 * @param {typeof groups[number]} group
	 * @param {number} index
	 * @param {boolean} [isAdvisor]
	 */
	function openOverlay(group, index, isAdvisor = false) {
		const offset = isAdvisor ? group.members.length + index : index;
		overlayGroup = group;
		overlayIndex = offset;
		if (browser) document.body.style.overflow = 'hidden';
		requestAnimationFrame(() => scrollToIndex(offset, false));
	}

	function closeOverlay() {
		overlayGroup = null;
		overlayIndex = 0;
		if (browser) document.body.style.overflow = '';
	}

	/**
	 * @param {number} idx
	 * @param {boolean} [smooth]
	 */
	function scrollToIndex(idx, smooth = true) {
		if (!scrollContainer) return;
		const cards = scrollContainer.children;
		if (cards[idx]) {
			cards[idx].scrollIntoView({
				behavior: smooth ? 'smooth' : 'instant',
				inline: 'center',
				block: 'nearest'
			});
		}
	}

	/** @param {number} dir */
	function navigate(dir) {
		if (!overlayGroup) return;
		const all = getAllMembers(overlayGroup);
		overlayIndex = (overlayIndex + dir + all.length) % all.length;
		scrollToIndex(overlayIndex);
	}

	/** @param {KeyboardEvent} e */
	function handleOverlayKeydown(e) {
		if (e.key === 'Escape') closeOverlay();
		if (e.key === 'ArrowLeft') navigate(-1);
		if (e.key === 'ArrowRight') navigate(1);
	}

	/** @param {MouseEvent} e */
	function handleBackdropClick(e) {
		if (e.target === e.currentTarget) closeOverlay();
	}

	function handleScroll() {
		if (!scrollContainer) return;
		const cards = scrollContainer.children;
		const containerRect = scrollContainer.getBoundingClientRect();
		const center = containerRect.left + containerRect.width / 2;
		let closest = 0;
		let minDist = Infinity;
		for (let i = 0; i < cards.length; i++) {
			const rect = cards[i].getBoundingClientRect();
			const cardCenter = rect.left + rect.width / 2;
			const dist = Math.abs(cardCenter - center);
			if (dist < minDist) {
				minDist = dist;
				closest = i;
			}
		}
		overlayIndex = closest;
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
			<div class="about-section">
				<h2>Meet the officers</h2>
				<div class="officers-grid">
					{#each officers as officer}
						<div class="officer-card">
							<div class="officer-avatar">
								{#if officer.image}
									<img src={officer.image} alt={officer.name} />
								{:else}
									<span class="officer-initials">
										{officer.name
											.split(' ')
											.map((n) => n[0])
											.join('')}
									</span>
								{/if}
							</div>
							<div class="officer-info">
								<p class="officer-name">{officer.name}</p>
								<p class="officer-role">{officer.role}</p>
							</div>
						</div>
					{/each}
				</div>
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
					{#each group.members as member, i}
						<button
							class="member-card"
							on:click={() => openOverlay(group, i)}
							type="button"
						>
							<div class="member-photo">
								{#if member.photo}
									<img src={member.photo} alt={member.name} />
								{:else}
									<span class="member-initials">{initials(member.name)}</span>
								{/if}
							</div>
							<div class="member-info">
								<p class="member-name">{member.name}</p>
								<p class="member-bio">{member.bio}</p>
							</div>
						</button>
					{/each}
				</div>

				{#if group.advisors.length}
					<div class="advisors-row">
						<p class="advisors-label">Advisors</p>
						<div class="advisors-grid">
							{#each group.advisors as advisor, i}
								<button
									class="advisor-card"
									on:click={() => openOverlay(group, i, true)}
									type="button"
								>
									<div class="advisor-avatar">
										{#if advisor.photo}
											<img src={advisor.photo} alt={advisor.name} />
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
								</button>
							{/each}
						</div>
					</div>
				{/if}
			</div>
		{/each}
	</div>
</section>

<!-- Overlay -->
{#if overlayGroup}
	<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
	<div
		class="overlay"
		role="dialog"
		aria-modal="true"
		style="--tc: {teamConfig[overlayGroup.id].color}"
		on:click={handleBackdropClick}
		on:keydown={handleOverlayKeydown}
		transition:fade={{ duration: 200 }}
	>
		<button class="overlay-close" on:click={closeOverlay} type="button" aria-label="Close">
			<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor"
				stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
				<line x1="18" y1="6" x2="6" y2="18" />
				<line x1="6" y1="6" x2="18" y2="18" />
			</svg>
		</button>

		<div class="overlay-team-label">
			<span class="team-pill">{teamConfig[overlayGroup.id].label}</span>
		</div>

		<button
			class="overlay-arrow overlay-arrow--left"
			on:click={() => navigate(-1)}
			type="button"
			aria-label="Previous member"
		>
			<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor"
				stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
				<polyline points="15 18 9 12 15 6" />
			</svg>
		</button>

		<button
			class="overlay-arrow overlay-arrow--right"
			on:click={() => navigate(1)}
			type="button"
			aria-label="Next member"
		>
			<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor"
				stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
				<polyline points="9 18 15 12 9 6" />
			</svg>
		</button>

		<div class="overlay-scroll" bind:this={scrollContainer} on:scroll={handleScroll}>
			{#each getAllMembers(overlayGroup) as person, i}
				<div class="overlay-card" class:overlay-card--active={i === overlayIndex}>
					<div class="overlay-photo">
						{#if person.photo}
							<img src={person.photo} alt={person.name} />
						{:else}
							<span class="overlay-initials">{initials(person.name)}</span>
						{/if}
					</div>
					<div class="overlay-details">
						{#if person.isAdvisor}
							<span class="overlay-badge">Advisor</span>
						{/if}
						<h3 class="overlay-name">{person.name}</h3>
						<p class="overlay-bio">{person.bio}</p>
					</div>
				</div>
			{/each}
		</div>

		<div class="overlay-dots">
			{#each getAllMembers(overlayGroup) as _, i}
				<button
					class="overlay-dot"
					class:overlay-dot--active={i === overlayIndex}
					on:click={() => { overlayIndex = i; scrollToIndex(i); }}
					type="button"
					aria-label="Go to member {i + 1}"
				/>
			{/each}
		</div>
	</div>
{/if}

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

	/* Officers */
	.officers-grid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
		gap: 1.5rem;
		margin-top: 2rem;
	}

	.officer-card {
		background: rgba(255, 255, 255, 0.04);
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: var(--radius-lg);
		padding: 2rem 1.5rem;
		text-align: center;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
		transition:
			transform var(--tr),
			border-color var(--tr),
			background var(--tr);
	}

	.officer-card:hover {
		transform: translateY(-4px);
		border-color: rgba(255, 184, 0, 0.35);
		background: rgba(255, 255, 255, 0.07);
	}

	.officer-avatar {
		width: 88px;
		height: 88px;
		border-radius: 50%;
		background: linear-gradient(135deg, var(--archimedes-yellow), var(--incandescent-gold));
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
		flex-shrink: 0;
	}

	.officer-avatar img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.officer-initials {
		font-size: 1.4rem;
		font-weight: 800;
		color: var(--steel);
		letter-spacing: 0.5px;
	}

	.officer-info {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
	}

	.officer-name {
		font-weight: 700;
		font-size: 1.1rem;
		color: var(--text-on-dark);
		margin: 0;
	}

	.officer-role {
		font-size: 0.8rem;
		font-weight: 600;
		text-transform: uppercase;
		letter-spacing: 1.2px;
		color: var(--archimedes-yellow);
		margin: 0;
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
		cursor: pointer;
		text-align: left;
		padding: 0;
		font: inherit;
		color: inherit;
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
		cursor: pointer;
		font: inherit;
		color: inherit;
		text-align: left;
		transition: background var(--tr);
	}

	.advisor-card:hover {
		background: rgba(255, 255, 255, 0.05);
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

	/* ── Overlay ── */
	.overlay {
		position: fixed;
		inset: 0;
		z-index: 100;
		background: rgba(10, 18, 20, 0.94);
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 1rem;
	}

	.overlay-close {
		position: absolute;
		top: 1.25rem;
		right: 1.25rem;
		background: rgba(255, 255, 255, 0.08);
		border: 1px solid rgba(255, 255, 255, 0.12);
		border-radius: 50%;
		width: 44px;
		height: 44px;
		display: flex;
		align-items: center;
		justify-content: center;
		color: rgba(255, 252, 242, 0.8);
		cursor: pointer;
		transition: background var(--tr);
		z-index: 2;
		padding: 0;
	}

	.overlay-close:hover {
		background: rgba(255, 255, 255, 0.15);
	}

	.overlay-team-label {
		position: absolute;
		top: 1.4rem;
		left: 1.25rem;
		z-index: 2;
	}

	.overlay-arrow {
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		background: rgba(255, 255, 255, 0.06);
		border: 1px solid rgba(255, 255, 255, 0.1);
		border-radius: 50%;
		width: 48px;
		height: 48px;
		display: flex;
		align-items: center;
		justify-content: center;
		color: rgba(255, 252, 242, 0.7);
		cursor: pointer;
		transition: background var(--tr);
		z-index: 2;
		padding: 0;
	}

	.overlay-arrow:hover {
		background: rgba(255, 255, 255, 0.12);
		color: #fff;
	}

	.overlay-arrow--left {
		left: 1rem;
	}

	.overlay-arrow--right {
		right: 1rem;
	}

	/* Scroll container */
	.overlay-scroll {
		display: flex;
		gap: 1.5rem;
		overflow-x: auto;
		scroll-snap-type: x mandatory;
		-webkit-overflow-scrolling: touch;
		max-width: 100%;
		width: 100%;
		padding: 2rem 4.5rem;
		scrollbar-width: none;
	}

	.overlay-scroll::-webkit-scrollbar {
		display: none;
	}

	/* Individual overlay card */
	.overlay-card {
		flex: 0 0 min(420px, 85vw);
		scroll-snap-align: center;
		background: rgba(255, 255, 255, 0.04);
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-top: 3px solid var(--tc);
		border-radius: var(--radius-lg);
		overflow: hidden;
		display: flex;
		flex-direction: column;
		opacity: 0.4;
		transform: scale(0.92);
		transition:
			opacity 0.3s ease,
			transform 0.3s ease;
	}

	.overlay-card--active {
		opacity: 1;
		transform: scale(1);
	}

	.overlay-photo {
		width: 100%;
		aspect-ratio: 1;
		max-height: 320px;
		background: rgba(255, 255, 255, 0.06);
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}

	.overlay-photo img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.overlay-initials {
		font-size: 4rem;
		font-weight: 800;
		color: var(--tc);
		letter-spacing: 2px;
	}

	.overlay-details {
		padding: 1.5rem;
		display: flex;
		flex-direction: column;
		gap: 0.6rem;
	}

	.overlay-badge {
		align-self: flex-start;
		font-size: 0.7rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		color: var(--tc);
		background: rgba(255, 255, 255, 0.06);
		border: 1px solid var(--tc);
		border-radius: 999px;
		padding: 0.2rem 0.65rem;
	}

	.overlay-name {
		font-size: 1.25rem;
		font-weight: 800;
		color: var(--text-on-dark);
		margin: 0;
	}

	.overlay-bio {
		font-size: 0.95rem;
		line-height: 1.7;
		color: rgba(255, 252, 242, 0.7);
		margin: 0;
	}

	/* Dots indicator */
	.overlay-dots {
		display: flex;
		gap: 0.4rem;
		margin-top: 1rem;
		z-index: 2;
	}

	.overlay-dot {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: rgba(255, 252, 242, 0.2);
		border: none;
		padding: 0;
		cursor: pointer;
		transition: background var(--tr);
	}

	.overlay-dot--active {
		background: var(--tc);
	}

	@media (max-width: 768px) {
		.officers-grid {
			grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
			gap: 1rem;
		}

		.officer-card {
			padding: 1.5rem 1rem;
		}

		.officer-avatar {
			width: 72px;
			height: 72px;
		}

		.officer-initials {
			font-size: 1.15rem;
		}

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

		.overlay-arrow {
			display: none;
		}

		.overlay-scroll {
			padding: 2rem 1.5rem;
			gap: 1rem;
		}

		.overlay-card {
			flex: 0 0 85vw;
		}

		.overlay-photo {
			max-height: 250px;
		}
	}

	@media (max-width: 480px) {
		.members-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
