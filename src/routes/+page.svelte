<script>
	const skillGroups = [
		{
			title: 'Backend',
			description: '서버 로직과 API를 설계하고 구현합니다.',
			skills: ['Python', 'FastAPI', 'Flask', 'MongoDB', 'SQLite']
		},
		{
			title: 'Frontend',
			description: '사용자가 보는 화면을 깔끔하게 구성합니다.',
			skills: ['Svelte', 'JavaScript', 'HTML', 'CSS', "TailwindCSS"]
		},
		{
			title: 'Minecraft',
			description: 'PvP 서버와 플러그인 시스템을 개발합니다.',
			skills: ['Kotlin', 'Paper API', 'Plugin Development']
		},
		{
			title: 'Infrastructure',
			description: '서비스 실행 환경과 배포 환경을 관리합니다.',
			skills: ['Docker', 'Ubuntu', "Debian", 'NGINX', 'Git', "Poetry"]
		}
	];
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div class="container">
	<h1 class="title">
		<span>안녕하세요</span>
		<span>저는 프마라고 합니다.</span>
	</h1>
</div>

<section class="content">
	<div class="section-header">
		<p class="eyebrow">기술 스택</p>
		<h1>Skills</h1>
	</div>

	<div class="skills-grid">
		{#each skillGroups as group}
			<article class="skill-card">
				<div>
					<h2>{group.title}</h2>
					<p>{group.description}</p>
				</div>

				<div class="skill-list">
					{#each group.skills as skill}
						<span>{skill}</span>
					{/each}
				</div>
			</article>
		{/each}
	</div>
</section>

<style>
	:global(body) {
		margin: 0;

		font-family:
				'Inter',
				'Pretendard',
				sans-serif;

		background:
				radial-gradient(
						circle at top,
						rgba(255, 255, 255, 0.8),
						#ececec 45%,
						#dddddd 100%
				);

		color: #111111;

		overflow-x: hidden;
	}

	.container {
		height: 90vh;

		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		text-align: center;

		padding: 0 1.5rem;
	}

	.title {
		display: flex;
		flex-direction: column;

		gap: 0.2rem;

		margin: 0;

		font-size: clamp(3.5rem, 8vw, 7rem);
		font-weight: 750;

		letter-spacing: -0.06em;
		line-height: 0.95;

		animation: fadeUp 1s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.title span {
		display: block;
	}

	.content {
		width: min(1100px, 92%);

		margin: 0 auto;
		padding: 5rem 0 8rem;
	}

	.section-header {
		text-align: center;

		margin-bottom: 3rem;

		animation: fadeUp 1s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.eyebrow {
		margin: 0 0 0.7rem;

		font-size: 0.78rem;
		font-weight: 700;

		letter-spacing: 0.16em;

		color: rgba(0, 0, 0, 0.45);
	}

	.section-header h1 {
		margin: 0;

		font-size: clamp(2.4rem, 5vw, 4.5rem);
		font-weight: 760;

		letter-spacing: -0.05em;
	}

	.section-header p:last-child {
		margin: 1rem 0 0;

		font-size: 1.05rem;
		font-weight: 500;

		color: rgba(0, 0, 0, 0.58);
	}

	.skills-grid {
		display: grid;
		grid-template-columns: repeat(2, minmax(0, 1fr));
		gap: 1rem;
	}

	.skill-card {
		min-height: 220px;

		display: flex;
		flex-direction: column;
		justify-content: space-between;

		padding: 1.5rem;

		border-radius: 28px;

		background: rgba(255, 255, 255, 0.62);

		backdrop-filter: blur(18px);
		-webkit-backdrop-filter: blur(18px);

		border: 1px solid rgba(0, 0, 0, 0.06);

		box-shadow:
				0 18px 45px rgba(0, 0, 0, 0.08),
				inset 0 1px 0 rgba(255, 255, 255, 0.7);

		transition:
				transform 0.45s cubic-bezier(0.22, 1, 0.36, 1),
				box-shadow 0.45s cubic-bezier(0.22, 1, 0.36, 1),
				background 0.45s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.skill-card:hover {
		transform: translateY(-8px) scale(1.015);

		background: rgba(255, 255, 255, 0.78);

		box-shadow:
				0 26px 70px rgba(0, 0, 0, 0.12),
				inset 0 1px 0 rgba(255, 255, 255, 0.8);
	}

	.skill-card h2 {
		margin: 0;

		font-size: 1.45rem;
		font-weight: 720;

		letter-spacing: -0.04em;
	}

	.skill-card p {
		margin: 0.7rem 0 0;

		font-size: 0.98rem;
		line-height: 1.6;

		color: rgba(0, 0, 0, 0.56);
	}

	.skill-list {
		display: flex;
		flex-wrap: wrap;
		gap: 0.55rem;

		margin-top: 2rem;
	}

	.skill-list span {
		padding: 0.55rem 0.8rem;

		border-radius: 999px;

		background: rgba(0, 0, 0, 0.055);

		color: rgba(0, 0, 0, 0.78);

		font-size: 0.88rem;
		font-weight: 600;

		transition:
				transform 0.3s cubic-bezier(0.22, 1, 0.36, 1),
				background 0.3s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.skill-card:hover .skill-list span {
		background: rgba(0, 0, 0, 0.075);
	}

	.skill-list span:hover {
		transform: scale(1.07);
	}

	@keyframes fadeUp {
		from {
			opacity: 0;

			transform:
					translateY(24px)
					scale(0.98);

			filter: blur(10px);
		}

		to {
			opacity: 1;

			transform:
					translateY(0)
					scale(1);

			filter: blur(0);
		}
	}

	@media (max-width: 760px) {
		.skills-grid {
			grid-template-columns: 1fr;
		}

		.skill-card {
			min-height: 190px;
		}
	}
</style>