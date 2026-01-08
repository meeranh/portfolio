<script lang="ts">
	import { Github, Linkedin, Mail, ExternalLink, Award, Shield, Trophy, Bug, MapPin, ChevronDown } from 'lucide-svelte';

	const navItems = [
		{ label: 'about', href: '#about' },
		{ label: 'experience', href: '#experience' },
		{ label: 'projects', href: '#projects' },
		{ label: 'achievements', href: '#achievements' },
		{ label: 'contact', href: '#contact' }
	];

	const certifications = [
		{ name: 'SecurityX / CASP+', issuer: 'CompTIA', url: 'https://www.credly.com/badges/b0a96693-b669-4783-931a-5100076438fb/linked_in_profile' },
		{ name: 'CEH v12', issuer: 'EC-Council', url: 'https://aspen.eccouncil.org/VerifyBadge?type=certification&a=9ZtrXXd09eSEEvys3NbgbM+oH1UEub2y/JE3Y4xZ7zQ=' },
		{ name: 'eJPT', issuer: 'INE Security', url: 'https://certs.ine.com/2a7275fd-2f58-4dea-99c0-c01c40d3e756' },
		{ name: 'PT1', issuer: 'TryHackMe', url: 'https://assets.tryhackme.com/certification-certificate/68afe5b73520f378958b93f7.pdf' },
		{ name: 'AZ-500', issuer: 'Microsoft', url: 'https://learn.microsoft.com/api/credentials/share/en-gb/notmeeranh/E9A3B58E156DDFEE?sharingId=AF645FB48840BB73' },
		{ name: 'AZ-900', issuer: 'Microsoft', url: 'https://learn.microsoft.com/api/credentials/share/en-us/notmeeranh/3D241D8BFECC17D1?sharingId' },
		{ name: 'CC', issuer: 'ISC²', url: 'https://www.credly.com/badges/edca8d5e-fbaa-463f-a717-3b8e40afac47/linked_in_profile' }
	];

	const skills = {
		'Security': ['Penetration Testing', 'VAPT', 'Code Review', 'SIEM', 'Bug Bounty'],
		'Languages': ['Go', 'Python', 'Rust', 'TypeScript', 'Lua', 'Bash'],
		'Cloud & IaC': ['Azure', 'Terraform', 'Docker', 'Sentinel'],
		'Frameworks': ['SvelteKit', 'Next.js', 'Express']
	};

	const projects = [
		{
			name: 'garden',
			description: 'A knowledge repository with easy-to-understand explanations of complex concepts',
			tech: ['Svelte', 'mdsvex', 'TypeScript'],
			url: 'https://github.com/meeranh/garden',
			live: 'https://garden.meeranh.com'
		},
		{
			name: 'plainsight',
			description: 'Post-quantum steganography tool using ML-KEM-768 and AES-256-GCM',
			tech: ['Svelte', 'TypeScript', 'WebCrypto'],
			url: 'https://github.com/meeranh/plainsight',
			live: 'https://plainsight.pages.dev'
		},
		{
			name: 'QuantumSign',
			description: 'Single Sign-On system based on quantum cryptography',
			tech: ['Python', 'Docker', 'PQC'],
			url: 'https://github.com/meeranh/QuantumSign'
		},
		{
			name: 'recycleMe',
			description: 'CLI tool to detect and humanize AI-generated text',
			tech: ['Go'],
			url: 'https://github.com/meeranh/recycleMe',
			stars: 21
		},
		{
			name: 'jwt-pq-backend',
			description: 'Rust API for benchmarking post-quantum JWT signature schemes',
			tech: ['Rust', 'PQC'],
			url: 'https://github.com/meeranh/jwt-pq-backend'
		},
		{
			name: 'LockUp',
			description: 'Client-side password manager with AES encryption',
			tech: ['JavaScript', 'WebCrypto'],
			url: 'https://github.com/meeranh/LockUp',
			live: 'https://meeranh.github.io/LockUp'
		}
	];

	const ctfAchievements = [
		{ name: 'SLIIT ISACA CTF', result: '1st Place', detail: 'Solo vs 15 four-member teams', highlight: true },
		{ name: 'CICRA 10th Summit CTF', result: '2nd Place', detail: 'Duo vs 40+ teams' },
		{ name: 'Enigma CTF', result: '2nd Place', detail: '19 participants' },
		{ name: 'Manthra CTF', result: '2nd Place', detail: '30+ participants' },
		{ name: 'Medusa CTF', result: '2nd Place', detail: '' }
	];

	const experience = [
		{
			title: 'Security Engineer & Penetration Tester',
			company: 'Surge Global',
			period: 'Nov 2023 - Present',
			points: [
				'Performed VAPT on in-house and client web applications',
				'Found 10-20 critical vulnerabilities per application on average',
				'Conducted security code reviews on client codebases',
				'Built Microsoft Sentinel SIEM solution with Terraform IaC'
			]
		},
		{
			title: 'Cyber Security Intern',
			company: 'Surge Global',
			period: 'May 2023 - Oct 2023',
			points: [
				'Performed VAPT on client applications',
				'Code review for vulnerability detection',
				'R&D on prompt injection prevention methods'
			]
		}
	];

	const education = [
		{ degree: 'MSc Network & Information Security', school: 'Kingston University', period: '2025' },
		{ degree: 'BSc (Hons) IT - Cyber Security', school: 'SLIIT', period: '2021 - 2024' }
	];
</script>

<!-- Navigation -->
<nav class="fixed top-0 left-0 right-0 z-50 bg-bg/90 backdrop-blur-sm border-b border-border">
	<div class="max-w-4xl mx-auto px-6 py-4 flex items-center justify-between">
		<a href="#" class="text-fg font-medium hover:text-aqua transition-colors">mh</a>
		<div class="flex gap-6">
			{#each navItems as item}
				<a
					href={item.href}
					class="text-fg-muted hover:text-aqua transition-colors text-sm"
				>
					{item.label}
				</a>
			{/each}
		</div>
	</div>
</nav>

<main class="max-w-4xl mx-auto px-6">
	<!-- Hero Section -->
	<section class="min-h-screen flex flex-col justify-center py-20 animate-in">
		<div class="flex flex-col md:flex-row items-center gap-8 md:gap-12">
			<img
				src="/profilePhoto.jpg"
				alt="Meeran Hassan"
				class="w-32 h-32 md:w-40 md:h-40 rounded-full border-2 border-border"
			/>
			<div class="text-center md:text-left">
				<h1 class="text-3xl md:text-4xl font-bold text-fg mb-2">Meeran Hassan</h1>
				<p class="text-xl text-aqua mb-4">Penetration Tester / Security Engineer</p>
				<p class="text-fg-muted flex items-center justify-center md:justify-start gap-2 mb-6">
					<MapPin class="w-4 h-4" />
					Sri Lanka
				</p>
				<p class="text-fg-muted max-w-lg leading-relaxed">
					Penetration tester specializing in web application security.
					Passionate about post-quantum cryptography and CTF competitions.
				</p>
				<div class="flex gap-4 mt-6 justify-center md:justify-start">
					<a href="https://github.com/meeranh" target="_blank" rel="noopener" class="text-fg-muted hover:text-aqua transition-colors">
						<Github class="w-5 h-5" />
					</a>
					<a href="https://linkedin.com/in/meeranh" target="_blank" rel="noopener" class="text-fg-muted hover:text-aqua transition-colors">
						<Linkedin class="w-5 h-5" />
					</a>
					<a href="mailto:career@meeranh.com" class="text-fg-muted hover:text-aqua transition-colors">
						<Mail class="w-5 h-5" />
					</a>
				</div>
			</div>
		</div>
		<a href="#about" class="absolute bottom-8 left-1/2 -translate-x-1/2 text-fg-muted hover:text-aqua transition-colors animate-bounce">
			<ChevronDown class="w-6 h-6" />
		</a>
	</section>

	<!-- About Section -->
	<section id="about" class="py-20 border-t border-border">
		<h2 class="text-2xl font-bold text-fg mb-2">about</h2>
		<div class="h-px bg-border mb-8"></div>

		<!-- Skills -->
		<div class="mb-12">
			<h3 class="text-fg-muted mb-4">skills</h3>
			<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
				{#each Object.entries(skills) as [category, items]}
					<div class="border border-border p-4 bg-bg-card">
						<h4 class="text-aqua text-sm mb-3">{category}</h4>
						<div class="flex flex-wrap gap-2">
							{#each items as skill}
								<span class="text-fg-muted text-sm px-2 py-1 border border-border">{skill}</span>
							{/each}
						</div>
					</div>
				{/each}
			</div>
		</div>

		<!-- Certifications -->
		<div class="mb-12">
			<h3 class="text-fg-muted mb-4">certifications</h3>
			<div class="grid grid-cols-2 md:grid-cols-3 gap-4">
				{#each certifications as cert}
					<a
						href={cert.url}
						target="_blank"
						rel="noopener"
						class="border border-border p-3 bg-bg-card flex items-center gap-3 hover:border-aqua transition-colors group"
					>
						<Shield class="w-4 h-4 text-green shrink-0" />
						<div>
							<p class="text-fg text-sm group-hover:text-aqua transition-colors">{cert.name}</p>
							<p class="text-fg-muted text-xs">{cert.issuer}</p>
						</div>
					</a>
				{/each}
			</div>
		</div>

		<!-- Education -->
		<div>
			<h3 class="text-fg-muted mb-4">education</h3>
			<div class="space-y-4">
				{#each education as edu}
					<div class="border border-border p-4 bg-bg-card">
						<p class="text-fg">{edu.degree}</p>
						<p class="text-fg-muted text-sm">{edu.school} &middot; {edu.period}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Experience Section -->
	<section id="experience" class="py-20 border-t border-border">
		<h2 class="text-2xl font-bold text-fg mb-2">experience</h2>
		<div class="h-px bg-border mb-8"></div>

		<div class="space-y-8">
			{#each experience as job}
				<div class="border border-border p-6 bg-bg-card">
					<div class="flex flex-col md:flex-row md:items-center md:justify-between mb-4">
						<div>
							<h3 class="text-fg font-medium">{job.title}</h3>
							<p class="text-aqua">{job.company}</p>
						</div>
						<p class="text-fg-muted text-sm">{job.period}</p>
					</div>
					<ul class="space-y-2">
						{#each job.points as point}
							<li class="text-fg-muted text-sm flex gap-2">
								<span class="text-aqua">&gt;</span>
								{point}
							</li>
						{/each}
					</ul>
				</div>
			{/each}
		</div>

		<!-- Bug Bounty -->
		<div class="mt-8 border border-border p-6 bg-bg-card">
			<div class="flex items-center gap-3 mb-4">
				<Bug class="w-5 h-5 text-orange" />
				<h3 class="text-fg font-medium">Bug Bounty</h3>
			</div>
			<div>
				<p class="text-fg">OpenSea - Sensitive Data Exposure</p>
				<p class="text-fg-muted text-sm mt-1">Found hardcoded credentials in JavaScript allowing authentication bypass</p>
				<p class="text-fg-muted text-xs mt-2">BugCrowd &middot; June 2024</p>
			</div>
		</div>
	</section>

	<!-- Projects Section -->
	<section id="projects" class="py-20 border-t border-border">
		<h2 class="text-2xl font-bold text-fg mb-2">projects</h2>
		<div class="h-px bg-border mb-8"></div>

		<div class="grid grid-cols-1 md:grid-cols-2 gap-4">
			{#each projects as project}
				<a
					href={project.url}
					target="_blank"
					rel="noopener"
					class="border border-border p-4 bg-bg-card hover:border-aqua transition-colors group"
				>
					<div class="flex items-start justify-between mb-2">
						<h3 class="text-fg group-hover:text-aqua transition-colors">{project.name}</h3>
						<div class="flex items-center gap-2">
							{#if project.stars}
								<span class="text-yellow text-xs">{project.stars} stars</span>
							{/if}
							{#if project.live}
								<a
									href={project.live}
									target="_blank"
									rel="noopener"
									class="text-fg-muted hover:text-aqua"
									onclick={(e) => e.stopPropagation()}
								>
									<ExternalLink class="w-4 h-4" />
								</a>
							{/if}
						</div>
					</div>
					<p class="text-fg-muted text-sm mb-3">{project.description}</p>
					<div class="flex flex-wrap gap-2">
						{#each project.tech as tech}
							<span class="text-xs text-aqua">{tech}</span>
						{/each}
					</div>
				</a>
			{/each}
		</div>

		<a
			href="https://github.com/meeranh?tab=repositories"
			target="_blank"
			rel="noopener"
			class="inline-flex items-center gap-2 mt-6 text-fg-muted hover:text-aqua transition-colors"
		>
			view all repositories <ExternalLink class="w-4 h-4" />
		</a>
	</section>

	<!-- Achievements Section -->
	<section id="achievements" class="py-20 border-t border-border">
		<h2 class="text-2xl font-bold text-fg mb-2">achievements</h2>
		<div class="h-px bg-border mb-8"></div>

		<div class="flex items-center gap-3 mb-6">
			<Trophy class="w-5 h-5 text-yellow" />
			<h3 class="text-fg-muted">capture the flag</h3>
		</div>

		<div class="space-y-3">
			{#each ctfAchievements as ctf}
				<div class="border border-border p-4 bg-bg-card flex items-center justify-between {ctf.highlight ? 'border-yellow' : ''}">
					<div>
						<p class="text-fg">{ctf.name}</p>
						{#if ctf.detail}
							<p class="text-fg-muted text-sm">{ctf.detail}</p>
						{/if}
					</div>
					<span class="text-sm {ctf.highlight ? 'text-yellow font-medium' : 'text-green'}">{ctf.result}</span>
				</div>
			{/each}
		</div>

		<p class="text-fg-muted text-sm mt-6">
			Consistently placed in the <span class="text-aqua">top 3</span> across all CTF competitions.
		</p>
	</section>

	<!-- Contact Section -->
	<section id="contact" class="py-20 border-t border-border">
		<h2 class="text-2xl font-bold text-fg mb-2">contact</h2>
		<div class="h-px bg-border mb-8"></div>

		<p class="text-fg-muted mb-8 max-w-lg">
			Interested in working together or have a security concern?
			Feel free to reach out.
		</p>

		<div class="flex flex-col sm:flex-row gap-4">
			<a
				href="mailto:career@meeranh.com"
				class="px-6 py-3 border border-border text-fg-muted hover:border-aqua hover:text-aqua transition-colors text-center"
			>
				career@meeranh.com
			</a>
			<a
				href="https://linkedin.com/in/meeranh"
				target="_blank"
				rel="noopener"
				class="px-6 py-3 border border-border text-fg-muted hover:border-aqua hover:text-aqua transition-colors flex items-center justify-center gap-2"
			>
				<Linkedin class="w-4 h-4" />
				LinkedIn
			</a>
		</div>
	</section>

	<!-- Footer -->
	<footer class="py-8 border-t border-border text-center">
		<p class="text-fg-muted text-sm">
			&copy; 2025 Meeran Hassan
		</p>
	</footer>
</main>
