<script>
	const projects = [
		{
			name: 'PVPCONNECT',
			desc: '현재 마인크래프트 PVP 연습 서버를 운영중입니다 (2024 ~ )',
			img: 'imgs/pvpconnect.webp',
			discord: 'https://discord.pvpconnect.xyz',
			link: 'https://minelist.kr/servers/pvpconnect.xyz',
			stack: ['Kotlin', 'Paper API', 'MongoDB', 'Linux']
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
	<h1>프로젝트</h1>
</section>

<section class="projects">
	{#each projects as project}
		<article class="project">
			<div class="imageWrap">
				<img src={project.img} alt={`${project.name} 로고`} />
			</div>

			<div class="content">
				<h2>{project.name}</h2>
				<p>{project.desc}</p>

				<ul class="stack">
					{#each project.stack as tech}
						<li>{tech}</li>
					{/each}
				</ul>

				<div class="actions">
					<a href={project.discord} target="_blank">디스코드</a>
					<a href={project.link} target="_blank">페이지</a>
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
		min-height: 70vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 0 clamp(1.5rem, 6vw, 6rem);
	}

	.hero h1 {
		margin: 0;
		font-size: clamp(4rem, 10vw, 8rem);
		font-weight: 760;
		letter-spacing: -0.07em;
		line-height: 0.9;
		animation: fadeUp 0.9s ease both;
	}

	.projects {
		width: min(1100px, calc(100% - 2rem));
		margin: 0 auto 8rem;
	}

	.project {
		display: grid;
		grid-template-columns: 0.9fr 1.1fr;
		gap: clamp(1.5rem, 4vw, 4rem);
		align-items: center;
		padding: clamp(1.2rem, 3vw, 2.2rem);
		border: 1px solid rgba(0, 0, 0, 0.08);
		border-radius: 28px;
		background: rgba(255, 255, 255, 0.62);
		box-shadow: 0 24px 80px rgba(0, 0, 0, 0.06);
		backdrop-filter: blur(18px);
		margin-bottom: clamp(1.5rem, 4vw, 4rem);
	}

	.imageWrap {
		aspect-ratio: 1 / 1;
		border-radius: 24px;
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}

	.imageWrap img {
		width: 62%;
		height: 62%;
		object-fit: contain;
		transition: transform 0.35s ease;
		border-radius: 20%;
	}

	.project:hover .imageWrap img {
		transform: scale(1.06) rotate(-2deg);
	}

	.content {
		padding: 0.5rem;
	}

	h2 {
		margin: 0;
		font-size: clamp(2rem, 4vw, 3.5rem);
		letter-spacing: -0.05em;
	}

	.content > p:not(.category) {
		max-width: 520px;
		margin: 1rem 0 0;
		color: #555;
		font-size: 1rem;
		line-height: 1.8;
	}

	.actions {
		display: flex;
		gap: 0.5rem;
		flex-wrap: wrap;
		margin-top: 2rem;
	}

	.actions a {
		padding: 0.8rem 1.1rem;
		border-radius: 10px;
		background: #141414;
		color: white;
		text-decoration: none;
		font-size: 0.92rem;
		font-weight: 600;
		transition:
				transform 0.2s ease,
				opacity 0.2s ease;
	}

	.actions a:hover {
		opacity: 0.86;
		transform: scale(1.05);
	}

	.stack {
		display: flex;
		flex-wrap: wrap;
		gap: 0.45rem;
		margin: 1.3rem 0 0;
		padding: 0;
		list-style: none;
	}

	.stack li {
		padding: 0.45rem 0.7rem;
		border-radius: 999px;
		background: rgba(20, 20, 20, 0.06);
		border: 1px solid rgba(20, 20, 20, 0.08);
		color: #333;
		font-size: 0.82rem;
		font-weight: 600;
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

	@media (max-width: 760px) {
		.hero {
			min-height: 55vh;
		}

		.project {
			grid-template-columns: 1fr;
		}

		.imageWrap {
			aspect-ratio: 16 / 10;
		}

		.imageWrap img {
			width: 42%;
			height: 42%;
		}
	}
</style>