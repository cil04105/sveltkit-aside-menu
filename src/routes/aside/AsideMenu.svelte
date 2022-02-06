<script>
	import IoIosAddCircleOutline from 'svelte-icons/io/IoIosAddCircleOutline.svelte';
	import IoIosArrowDropleft from 'svelte-icons/io/IoIosArrowDropleft.svelte';
	import IoIosAddCircle from 'svelte-icons/io/IoIosAddCircle.svelte';
	import IoIosAdd from 'svelte-icons/io/IoIosAdd.svelte';
	import IoIosArrowDropright from 'svelte-icons/io/IoIosArrowDropright.svelte';
	import FaBuromobelexperte from 'svelte-icons/fa/FaBuromobelexperte.svelte';
	import FaFacebookMessenger from 'svelte-icons/fa/FaFacebookMessenger.svelte';
	import IoIosChatbubbles from 'svelte-icons/io/IoIosChatbubbles.svelte';
	import FaApple from 'svelte-icons/fa/FaApple.svelte';
	import FaBook from 'svelte-icons/fa/FaBook.svelte';
	import FaCalendarAlt from 'svelte-icons/fa/FaCalendarAlt.svelte';
	import FaRegBell from 'svelte-icons/fa/FaRegBell.svelte';
	import { open } from '$lib/myStore';
	import { fly, slide } from 'svelte/transition';

	const MENU = [
		{ id: 1, icon: FaBuromobelexperte, category: 'Dashboard', subCategory: [''] },
		{ id: 2, icon: FaFacebookMessenger, category: 'Messages', subCategory: [''] },
		{ id: 3, icon: IoIosChatbubbles, category: 'Chat', subCategory: [''] },
		{ id: 4, icon: FaApple, category: 'Challenges', subCategory: [''] },
		{
			id: 5,
			icon: FaBook,
			category: 'Classed',
			subCategory: ['Maths', 'English', 'Economics', 'Accounts']
		},
		{ id: 6, icon: FaCalendarAlt, category: 'Timetable', subCategory: [''] },
		{ id: 7, icon: FaRegBell, category: 'Notigications', subCategory: [''] }
	];

	// let $open = true;

	// const handelCategory = () => {
	// 	$open = !$open;
	// };
	const handelCategory = () => {
		$open = !$open;
	};

	let name = '';
</script>

<div
	class=" relative float-left ml-6 mt-6 p-7 opacity-90 text-gray-400  bg-gray-700  rounded-xl shadow-sm "
>
	<div class="flex mb-6 " class:justify-center={!$open} class:ml-4={!$open}>
		<div class="w-3 h-3 bg-red-500 rounded-full mr-1.5 drop-shadow-xl" />
		<div class="w-3 h-3 bg-yellow-500 rounded-full mr-1.5 drop-shadow-xl" />
		<div class="w-3 h-3 bg-green-500 rounded-full mr-1.5 drop-shadow-xl" />
	</div>

	<div class="w-80 relative h-screen toggleMotion" class:w-40={!$open}>
		<header class=" flex mb-6">
			<div class="w-14" class:m-auto={!$open} class:ml-14={!$open}>
				<img
					class="rounded-xl"
					src="https://images.unsplash.com/photo-1457449940276-e8deed18bfff?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
					alt="userImg"
				/>
			</div>

			<div class="flex pl-2 pt-4"><strong>{$open ? 'Peter' : ''}</strong></div>

			<!-- <div class="w-8 relative left-56"> -->
			<span
				class=" w-8 text-purple-500 arrow-motion absolute top-4 -right-10 "
				on:click={() => {
					handelCategory();
				}}
			>
				<!-- 전체 영역 안에다 relative 주는게 편함 -->
				{#if $open}
					<IoIosArrowDropleft />
				{:else}
					<IoIosArrowDropright />
				{/if}
			</span>
		</header>

		<hr class="mb-6" />

		<nav class="mb-6">
			{#each MENU as { id, icon, category, subCategory }}
				<ul>
					<li
						class:m-auto={!$open}
						class:w-8={!$open}
						class:h-8={!$open}
						class:mb-4={!$open}
						on:click={() => {
							name = category;
						}}
					>
						<span class="w-10 h-10 pt-1 pb-1 inline-block">
							<svelte:component this={icon} />
						</span>
						{#if $open}
							<p transition:fly={{ duration: 0 }} class="inline-block relative -top-3 ">
								{category}
							</p>
						{/if}
					</li>

					{#each subCategory as subCategory}
						<ul>
							<li class="ml-12">{name === category ? subCategory : ''}</li>
						</ul>
					{/each}
				</ul>
			{/each}
		</nav>
		<hr class="mb-14" />

		<footer class="m-8 ">
			<div
				class="p-10 rounded-xl"
				class:border-dashed={$open}
				class:border-2={$open}
				class:border-gray-700={!$open}
			>
				<div
					class="mb-4 mr- text-purple-500 h-10 w-10 "
					class:m-auto={$open}
					class:mr-60={!$open}
					class:-ml-2={!$open}
				>
					<IoIosAddCircle />
				</div>
				<p class="text-lg text-center" class:-ml-4={!$open}>
					{$open ? 'Upload new class' : 'Upload'}
				</p>
			</div>
		</footer>
	</div>
</div>

<style>
	.toggleMotion {
		transition: width 1s;
	}

	.arrow-motion {
		transition: x 1s;
	}
</style>
