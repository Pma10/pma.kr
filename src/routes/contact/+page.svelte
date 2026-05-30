<script>
	const email = 'me@pma.kr';
	const discord = '@pma10';
	const discordUrl = 'https://discord.com/users/959696962523914260';
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

<section class="hero">
	<div class="intro">
		<h1>CONTACT</h1>
	</div>

	<div class="contacts">
		<a href={`mailto:${email}`} class="contact">
			<div>
				<div class="meta">EMAIL</div>
				<div class="value">{email}</div>
			</div>
			<span class="arrow">↗</span>
		</a>

		<a href={discordUrl} target="_blank" rel="noopener noreferrer" class="contact">
			<div>
				<div class="meta">DISCORD</div>
				<div class="value">{discord}</div>
			</div>
			<span class="arrow">↗</span>
		</a>
	</div>
</section>

<style>
	.hero {
		min-height: 85vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: clamp(2rem, 5vw, 5rem);
		max-width: 1200px;
		margin: 0 auto;
	}

	.intro {
		animation: fadeUp 0.8s cubic-bezier(.16, 1, .3, 1) both;
	}

	.hero h1 {
		margin: 0;
		font-size: clamp(4rem, 12vw, 9rem);
		font-weight: 800;
		letter-spacing: -0.08em;
		line-height: 0.9;
	}

	.contacts {
		margin-top: 3rem;
		max-width: 850px;
		animation: fadeUp 0.8s cubic-bezier(.16, 1, .3, 1) 0.12s both;
	}

	.contact {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1.4rem 0;
		text-decoration: none;
		color: inherit;
		border-top: 1px solid rgba(127, 127, 127, 0.2);
		transition:
				padding-left 0.25s ease,
				border-color 0.25s ease,
				opacity 0.25s ease;
	}

	.contact:last-child {
		border-bottom: 1px solid rgba(127, 127, 127, 0.2);
	}

	.contact:hover {
		padding-left: 0.9rem;
		border-color: rgba(127, 127, 127, 0.45);
	}

	.meta {
		font-size: 0.75rem;
		font-weight: 700;
		letter-spacing: 0.28em;
		text-transform: uppercase;
		opacity: 0.55;
		color: currentColor;
	}

	.value {
		margin-top: 0.35rem;
		font-size: clamp(1.05rem, 1.8vw, 1.4rem);
		font-weight: 600;
		color: currentColor;
	}

	.arrow {
		font-size: 1.2rem;
		opacity: 0.45;
		transform: translate(-6px, 6px);
		transition:
				transform 0.25s ease,
				opacity 0.25s ease;
	}

	.contact:hover .arrow {
		transform: translate(0, 0);
		opacity: 1;
	}

	@keyframes fadeUp {
		from {
			opacity: 0;
			transform: translateY(24px);
			filter: blur(8px);
		}

		to {
			opacity: 1;
			transform: translateY(0);
			filter: blur(0);
		}
	}

	@media (max-width: 700px) {
		.hero {
			min-height: 75vh;
		}

		.contacts {
			margin-top: 2rem;
		}

		.contact {
			align-items: flex-start;
			gap: 1rem;
		}
	}
</style>