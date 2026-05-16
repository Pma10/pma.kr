<header>
	<nav class="navbar">
		<ul class="nav-links">
			<li><a href="/">About</a></li>
			<li><a href="/projects">Projects</a></li>
			<li><a href="/contact">Contact</a></li>
		</ul>
	</nav>
</header>

<style>
	:global(body) {
		margin: 0;

		font-family:
				'Inter',
				'Pretendard',
				sans-serif;

		background: linear-gradient(
				to bottom,
				#f5f5f5,
				#e9e9e9
		);

		min-height: 300vh;

		overflow-x: hidden;
	}

	.navbar {
		position: fixed;

		top: 1.4rem;
		left: 50%;

		transform: translateX(-50%);

		z-index: 1000;
	}

	.nav-links {
		display: flex;
		align-items: center;
		gap: 0.4rem;

		list-style: none;

		padding: 0.5rem;
		margin: 0;

		border-radius: 999px;

		background: rgba(255, 255, 255, 0.72);

		backdrop-filter: blur(18px);
		-webkit-backdrop-filter: blur(18px);

		border: 1px solid rgba(0, 0, 0, 0.06);

		box-shadow:
				0 10px 30px rgba(0, 0, 0, 0.08),
				0 2px 8px rgba(0, 0, 0, 0.04);

		animation: navAppear 0.8s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.nav-links a {
		position: relative;

		display: block;

		padding: 0.72rem 1.15rem;

		border-radius: 999px;

		text-decoration: none;

		color: #111111;

		font-size: 0.94rem;
		font-weight: 550;

		letter-spacing: -0.01em;

		transition:
				background 0.35s cubic-bezier(0.22, 1, 0.36, 1),
				transform 0.35s cubic-bezier(0.22, 1, 0.36, 1),
				box-shadow 0.35s cubic-bezier(0.22, 1, 0.36, 1),
				color 0.35s cubic-bezier(0.22, 1, 0.36, 1);

		will-change: transform;
	}

	.nav-links a::before {
		content: '';

		position: absolute;
		inset: 0;

		border-radius: inherit;

		background: linear-gradient(
				to bottom,
				rgba(255, 255, 255, 0.55),
				rgba(255, 255, 255, 0)
		);

		opacity: 0;

		transition:
				opacity 0.35s cubic-bezier(0.22, 1, 0.36, 1);
	}

	.nav-links a:hover {
		background: rgba(0, 0, 0, 0.06);

		transform:
				translateY(-2px)
				scale(1.04);

		box-shadow:
				0 8px 18px rgba(0, 0, 0, 0.08);
	}

	.nav-links a:hover::before {
		opacity: 1;
	}

	.nav-links a:active {
		transform: scale(0.96);

		transition-duration: 0.12s;
	}

	@keyframes navAppear {
		from {
			opacity: 0;

			transform:
					translateY(-14px)
					scale(0.94);

			filter: blur(8px);
		}

		to {
			opacity: 1;

			transform:
					translateY(0)
					scale(1);

			filter: blur(0);
		}
	}
</style>