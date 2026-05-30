<script>
	const projects = [
		{
			name: 'PVPCONNECT',
			desc: '현재 마인크래프트 PVP 연습 서버를 운영중입니다 (2024 ~ )',
			img: 'imgs/pvpconnect.webp',
			discord: 'https://discord.pvpconnect.xyz',
			link: 'https://minelist.kr/servers/pvpconnect.xyz',
			stack: ['Kotlin', 'Paper API', 'MongoDB', 'Linux', 'FastAPI', 'Socket']
		},
		{
			name: 'Chez',
			desc: '디스코드 치지직 알림봇입니다.',
			img: 'imgs/chez.png',
			discord: 'https://discord.gg/Jh2CVWAYkB',
			link: 'https://koreanbots.dev/bots/1206535811181318225',
			stack: ['Python', 'Discord.py', 'Docker']
		}
	];
</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<section class="hero">
	<h1>PROJECTS</h1>
</section>

<section class="projects">
	{#each projects as project, i}
		<article class="project" style={`--delay: ${i * 0.12}s`}>
			<div class="imageWrap">
				<img src={project.img} alt={`${project.name} 로고`} />
			</div>

			<div class="content">
				<div class="number">0{i + 1}</div>
				<h2>{project.name}</h2>
				<p>{project.desc}</p>

				<ul class="stack">
					{#each project.stack as tech}
						<li>{tech}</li>
					{/each}
				</ul>

				<div class="actions">
					<a href={project.discord} target="_blank" rel="noopener noreferrer">디스코드 ↗</a>
					<a href={project.link} target="_blank" rel="noopener noreferrer">페이지 ↗</a>
				</div>
			</div>
		</article>
	{/each}
</section>

<style>
	:global(body) {
		margin: 0;
		font-family: 'Inter', 'Pretendard', sans-serif;
		background: #f4f4f1;
		color: #141414;
		overflow-x: hidden;
	}

	.hero {
		min-height: 54vh;
		display: flex;
		flex-direction: column;
		justify-content: end;
		padding: 0 clamp(1.5rem, 6vw, 6rem) 4rem;
		max-width: 1280px;
		margin: 0 auto;
	}

	.hero span {
		margin-bottom: 0.8rem;
		font-size: 0.78rem;
		font-weight: 700;
		letter-spacing: 0.32em;
		opacity: 0.48;
		animation: fadeUp 0.8s cubic-bezier(.16, 1, .3, 1) both;
	}

	.hero h1 {
		margin: 0;
		font-size: clamp(4rem, 12vw, 10rem);
		font-weight: 820;
		letter-spacing: -0.085em;
		line-height: 0.82;
		animation: fadeUp 0.9s cubic-bezier(.16, 1, .3, 1) 0.08s both;
	}

	.projects {
		width: min(1120px, calc(100% - 3rem));
		margin: 0 auto 6rem;
		display: flex;
		flex-direction: column;
		gap: 1.2rem;
	}

	.project {
		position: relative;
		display: grid;
		grid-template-columns: 0.82fr 1.18fr;
		gap: clamp(1.2rem, 3vw, 3rem);
		align-items: center;
		padding: clamp(1.1rem, 2.6vw, 2rem);
		border: 1px solid rgba(20, 20, 20, 0.08);
		border-radius: 30px;
		background: rgba(255, 255, 255, 0.55);
		box-shadow: 0 18px 70px rgba(0, 0, 0, 0.055);
		backdrop-filter: blur(18px);
		overflow: hidden;
		animation: cardIn 0.85s cubic-bezier(.16, 1, .3, 1) var(--delay) both;
		transition:
				transform 0.28s ease,
				box-shadow 0.28s ease,
				border-color 0.28s ease;
	}

	.project::before {
		content: '';
		position: absolute;
		inset: 0;
		background:
				radial-gradient(circle at 18% 20%, rgba(255, 255, 255, 0.9), transparent 18rem),
				linear-gradient(120deg, rgba(255, 255, 255, 0.45), transparent);
		opacity: 0;
		transition: opacity 0.3s ease;
		pointer-events: none;
	}

	.project:hover {
		transform: translateY(-6px);
		border-color: rgba(20, 20, 20, 0.16);
		box-shadow: 0 28px 90px rgba(0, 0, 0, 0.085);
	}

	.project:hover::before {
		opacity: 1;
	}

	.imageWrap {
		position: relative;
		aspect-ratio: 1 / 1;
		border-radius: 24px;
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
		background:
				linear-gradient(145deg, rgba(20, 20, 20, 0.045), rgba(255, 255, 255, 0.45));
		border: 1px solid rgba(20, 20, 20, 0.06);
	}

	.imageWrap img {
		width: 58%;
		height: 58%;
		object-fit: contain;
		border-radius: 20%;
		transition:
				transform 0.45s cubic-bezier(.16, 1, .3, 1),
				filter 0.45s ease;
	}

	.project:hover .imageWrap img {
		transform: scale(1.08) rotate(-2deg);
		filter: drop-shadow(0 18px 25px rgba(0, 0, 0, 0.12));
	}

	.content {
		position: relative;
		z-index: 1;
		padding: 0.4rem;
	}

	.number {
		margin-bottom: 0.6rem;
		font-size: 0.75rem;
		font-weight: 800;
		letter-spacing: 0.22em;
		opacity: 0.4;
	}

	h2 {
		margin: 0;
		font-size: clamp(2.1rem, 5vw, 4rem);
		font-weight: 800;
		letter-spacing: -0.06em;
		line-height: 0.95;
	}

	.content > p {
		max-width: 540px;
		margin: 1rem 0 0;
		color: #555;
		font-size: 1rem;
		line-height: 1.8;
	}

	.stack {
		display: flex;
		flex-wrap: wrap;
		gap: 0.45rem;
		margin: 1.35rem 0 0;
		padding: 0;
		list-style: none;
	}

	.stack li {
		padding: 0.45rem 0.72rem;
		border-radius: 999px;
		background: rgba(20, 20, 20, 0.055);
		border: 1px solid rgba(20, 20, 20, 0.075);
		color: #333;
		font-size: 0.8rem;
		font-weight: 700;
		transition:
				transform 0.2s ease,
				background 0.2s ease;
	}

	.project:hover .stack li {
		background: rgba(20, 20, 20, 0.075);
	}

	.stack li:hover {
		transform: translateY(-2px);
	}

	.actions {
		display: flex;
		gap: 0.55rem;
		flex-wrap: wrap;
		margin-top: 1.8rem;
	}

	.actions a {
		padding: 0.82rem 1.05rem;
		border-radius: 999px;
		background: #141414;
		color: white;
		text-decoration: none;
		font-size: 0.9rem;
		font-weight: 700;
		transition:
				transform 0.22s ease,
				opacity 0.22s ease;
	}

	.actions a:hover {
		opacity: 0.86;
		transform: translateY(-2px);
	}

	@keyframes fadeUp {
		from {
			opacity: 0;
			transform: translateY(20px);
			filter: blur(8px);
		}

		to {
			opacity: 1;
			transform: translateY(0);
			filter: blur(0);
		}
	}

	@keyframes cardIn {
		from {
			opacity: 0;
			transform: translateY(34px) scale(0.98);
			filter: blur(10px);
		}

		to {
			opacity: 1;
			transform: translateY(0) scale(1);
			filter: blur(0);
		}
	}

	@media (max-width: 760px) {
		.hero {
			min-height: 38vh;
			padding-bottom: 2.5rem;
		}

		.projects {
			width: min(100% - 2rem, 1120px);
			margin-bottom: 4rem;
		}

		.project {
			grid-template-columns: 1fr;
			border-radius: 24px;
		}

		.imageWrap {
			aspect-ratio: 16 / 9;
		}

		.imageWrap img {
			width: 42%;
			height: 42%;
		}
	}
</style>