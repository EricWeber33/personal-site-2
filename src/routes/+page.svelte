<script lang="ts">
	import { Avatar } from "@skeletonlabs/skeleton";
	import Project from "$lib/components/Project.svelte";
	import GithubRepo from "$lib/components/GithubRepo.svelte";
	

	/** @type {import('./$types').PageData} */
	export let data:any;
  	$:data;
	let repos = data.repositories;
	let reposIndex:number = 0;
	let repoPgSize:number = 3;
	let pgSizes = [1, 3, 5, 10]

	$:reposIndex;
	$:repoPgSize;

	function reposNext() {
		reposIndex = (reposIndex + repoPgSize) % repos.length;
	}

	function reposPrev() {
		if (reposIndex < repoPgSize) {
			reposIndex += repos.length;
		}
		reposIndex = (reposIndex - repoPgSize) % repos.length;
	}
</script>

<div class="m-10 flex h-screen flex-col items-center">
	<div id='about-me'>
		<Avatar src="portrait.jpg" class="m-auto" width="w-72" initials="EW"></Avatar>
		<h1 class="text-6xl font-serif font-bold text-center">
			<span class="bg-gradient-to-br from-primary-500 to-secondary-500 bg-clip-text text-transparent box-decoration-clone">Eric Weber</span>
		</h1>
		<h1 class="text-4xl font-sans text-center">
			<span class="text-4xl">Software Developer</span>
		</h1>
		<hr class="my-4 bg-primary-500 border-none h-2">
		<div class="card-p4 variant-ringed max-w-md p-2 m-auto">
			<div class="card-p4 variant-ringed-secondary p-4">
				<p class="text-center text-lg">
					Hello! I am a passionate software developer with an interest in a variety of technologies for both frontend and backend development.
					I have recently graduated from the University of Alberta with a specialization in computing science and am looking to leverage the knowledge and skills
					I have acquired to build the future.
				</p>
			</div>
		</div>
		<hr class="my-4 bg-primary-500 border-none h-2">
		<div class="flex-col lg:flex-row flex lg:space-x-2">
			<div class="flex flex-row mx-auto">
				<svg class="fill-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
				</svg>
				<span class="mx-2 text-lg hover:bg-gradient-to-t from-secondary-500 from-10% to-10%"><a href="https://www.linkedin.com/in/eric-weber33/">LinkedIn</a></span>
			</div>
			<div class="flex flex-row mx-auto">
				<svg class="fill-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path d="M12 12.713l-11.985-9.713h23.97l-11.985 9.713zm0 2.574l-12-9.725v15.438h24v-15.438l-12 9.725z"/>
				</svg>
				<span class="mx-2 text-lg hover:bg-gradient-to-t from-secondary-500 from-10% to-10%"><a href="mailto:edweber@ualberta.ca">edweber@ualberta.ca</a></span>
			</div>
			<div class="flex flex-row mx-auto">
				<svg class ="fill-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
				</svg>
				<span class="mx-2 text-lg hover:bg-gradient-to-t from-secondary-500 from-10% to-10%"><a href="https://github.com/EricWeber33">Github</a></span>
			</div>
			<div class="flex flex-row mx-auto">
				<svg class="fill-white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
					<path d="M7 2v-2h10v2h-10zm0 4h10v-2h-10v2zm10 7v-5h-10v5h-6l11 11 11-11h-6z"/>
				</svg>
				<span class="mx-2 text-lg hover:bg-gradient-to-t from-secondary-500 from-10% to-10%"><a href="Resume.pdf" download="eric-weber-resume.pdf">Resume</a></span>
			</div>
		</div>
		<hr class="my-4 bg-primary-500 border-none h-2">
	</div>
	<div id="experience" class="m-10">
		<h2 class="text-5xl font-serif my-4">Experience:</h2>
		<div class="flex flex-row">
			<div class="bg-gradient-to-b from-primary-500 to-secondary-500 max-w-80 p-4 text-black max-w-[600px]">
				<h2 class=" text-2xl lg:text-4xl font-serif font-extrabold">
					<span>
						Software Developer Intern
					</span>
				</h2>
				<p class="text-lg lg:text-xl font-bold">
					HCL / Dell-EMC
				</p>
				<p class="my-2 text-md lg:text-lg">
					<b>VPLEX project:</b> Worked on UI for a mature, enterprise level, storage-virtualization and protection product.
				</p>
				<ul class="list-disc mx-4 text-md lg:text-lg">
					<li>Developed web-GUI as well as CLI features.</li>
					<li>Ensured software quality by writing unit, integration, system, and acceptance tests.</li>
					<li>Maintained testing infrastructure used by multiple teams.</li>
				</ul>
				<p class="my-2 text-md lg:text-lg">
					<b>Skills:</b> Angular, Docker, Java, Linux, Python
				</p>
			</div>
			<!-- svelte-ignore a11y-missing-attribute -->
			<img class="flex-1 hidden max-h-[330px] lg:block" src="vplex.jfif"/>
		</div>
	</div>
	<div id="projects" class="m-10 text-left w-full">
		<h2 class="text-5xl font-serif mx-10 mb-4 text-center">
			Projects
		</h2>
		<div class="flex flex-wrap">
			<Project imgSrc="communakit.png" link="https://cmput401.ca/projects/6dfd54f3-7e8b-4c5a-a395-1afe14b8e061">
				<span slot="name">Communakit</span>
				<span slot="description">
					App developed in my software processes and management class in partnership with Communakit,
					an Edmonton based startup that makes speech therapy kits for children. This app is a cross-platform mobile
					app that acts as a companion to their core product line, allowing educators to conveniently do lessons and
					track learning progress with their students. I was the main backend developer as well as the product owner for this project.
				</span>
			</Project>
			<Project imgSrc="social-dist.jpg" link="https://github.com/EricWeber33/cmput404_project">
				<span slot="name">Social Distribution</span>
				<span slot="description">
					Web twitter clone that can act in a federated way with other sites sharing the same API.
					Built as part of a web-development class. Users can make and view posts as well as follow other
					users. These features also works for sites from other groups in the class. 
				</span>
			</Project>
			<Project imgSrc="3dayslate.jpg" link="https://drive.google.com/file/d/1nxr9YhmvDhNg-_iDsYONyMoPHNATfSi_/view">
				<span slot="name">Book Sharing App</span>
				<span slot="description">
					Book sharing service where users can lend and request books from other users.
					To get started, users must create an account using an email and a unique username.
					Users can either add a book via scanning or by inputting an ISBN. Books in the app
					can then be viewed and requested by other users. The app will also handle the process of borrowing
					and returning books between owners and borrowers.
				</span>
			</Project>
			<Project imgSrc="filesys.png" link="https://github.com/EricWeber33/file-system-monitor">
				<span slot="name">File System Monitor</span>
				<span slot="description">
					Linux File system monitor built with c. Observers are instantiated to monitor 
					files via inotify, which send data to the server via TCP. Users can connect to the sever to see the output
					of all the observers in a terminal-user-interface.
				</span>
			</Project>
		</div>



	</div>
	<div id="github-feed" class="card p-4 my-10 w-full">
		<h2 class="text-4xl font-serif">
			<span class="bg-gradient-to-b from-primary-500 to-secondary-500 bg-clip-text text-transparent box-decoration-clone">My Github Repos:</span>
		</h2>
		{#each  {length: repoPgSize} as _, i}
			<GithubRepo repo={repos[(reposIndex + i) % repos.length]}/>
		{/each}
		<div class="flex flex-col md:flex-row space-2 relative">
			<div class="w-full md:w-[50%] md:absolute md:left-0">
				<label class="label flex flex-row justify-end md:justify-normal">
					<span class="my-auto">Displaying:</span>
					<select class="select w-32 ml-2" bind:value={repoPgSize}>
						{#each pgSizes as size}
							{#if size === repoPgSize}
								<option selected value={size}>{size}</option>
							{:else}
								<option value={size}>{size}</option>
							{/if}
						{/each}
					</select>
				</label>
			</div>
			<div class="flex flex-row justify-end w-full space-x-2 my-2 md:my-0">
				<div class="hidden m-0 p-0 my-auto sm:block">
					{#if repoPgSize === 1}
						<span class="my-auto mx-2">Showing repo {reposIndex + 1} of {repos.length} </span>
					{:else}
						<span class="my-auto mx-2">Showing repos {reposIndex + 1} - {((reposIndex + repoPgSize) % repos.length) + 1} of {repos.length} </span>
					{/if}
				</div>
				<button class="btn-lg bg-primary-500 hover:bg-primary-400" on:click={reposPrev}>back</button>
				<button class="btn-lg bg-primary-500 hover:bg-primary-400" on:click={reposNext}>next</button>
			</div>
		</div>
	</div>
	<div class="h-64">

	</div>
</div>
