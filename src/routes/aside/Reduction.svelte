<script>
	import IoIosAddCircleOutline from 'svelte-icons/io/IoIosAddCircleOutline.svelte';
	import IoIosArrowDropleft from 'svelte-icons/io/IoIosArrowDropleft.svelte';
	import IoIosArrowDropright from 'svelte-icons/io/IoIosArrowDropright.svelte';
	import IoIosAddCircle from 'svelte-icons/io/IoIosAddCircle.svelte';
	import FaBuromobelexperte from 'svelte-icons/fa/FaBuromobelexperte.svelte';
	import FaFacebookMessenger from 'svelte-icons/fa/FaFacebookMessenger.svelte';
	import IoIosChatbubbles from 'svelte-icons/io/IoIosChatbubbles.svelte';
	import FaApple from 'svelte-icons/fa/FaApple.svelte';
	import FaBook from 'svelte-icons/fa/FaBook.svelte';
	import FaCalendarAlt from 'svelte-icons/fa/FaCalendarAlt.svelte';
	import FaRegBell from 'svelte-icons/fa/FaRegBell.svelte';
	// import { fly, slide } from 'svelte/transition';

	const MENU = [
		{ id: 1, category: 'Dashboard', subCategory: [''] },
		{ id: 2, category: 'Messages', subCategory: [''] },
		{ id: 3, category: 'Chat', subCategory: [''] },
		{ id: 3, category: 'Challenges', subCategory: [''] },
		{ id: 5, category: 'Classed', subCategory: ['Maths', 'English', 'Economics', 'Accounts'] },
		{ id: 6, category: 'Timetable', subCategory: [''] },
		{ id: 7, category: 'Notigications', subCategory: [''] }
	];

	// let subCategoryOpen = true;
	// const handelCategory = () => {
	// 	subCategoryOpen = !subCategoryOpen;
	// };
	let open = true;

	const handelCategory = () => {
		open = !open;
	};

	let name = '';
</script>

{open}
<div
	class=" relative float-left ml-6 mt-6 p-7 opacity-90 text-gray-400  bg-gray-700  rounded-xl shadow-sm "
>
	<div class="w-20  p-2 h-screen">
		<header class=" flex mb-6">
			<div class="w-14 m-auto">
				<img
					class="rounded-xl "
					src="https://images.unsplash.com/photo-1457449940276-e8deed18bfff?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
					alt="userImg"
				/>
			</div>
		</header>
		<hr class="mb-6" />

		<nav class="mb-6  ">
			<ul>
				<li class="mb-4 m-auto w-8 h-8"><FaBuromobelexperte /></li>
				<li class="mb-4 m-auto w-8 h-8"><FaFacebookMessenger /></li>
				<li class="mb-4 m-auto w-8 h-8"><IoIosChatbubbles /></li>
				<li class="mb-4 m-auto w-8 h-8"><FaApple /></li>
				<li class="mb-4 m-auto w-8 h-8"><FaBook /></li>
				<li class="mb-4 m-auto w-8 h-8"><FaCalendarAlt /></li>
				<li class="mb-4 m-auto w-8 h-8"><FaRegBell /></li>
			</ul>
		</nav>
		<hr class="mb-24" />

		<footer>
			<div class="border-dashed rounded-xl">
				<div class="m-auto mb-4 text-purple-500 h-10 w-10">
					<IoIosAddCircle />
				</div>
				<p class="text-lg text-center">Upload</p>
			</div>
		</footer>
	</div>
</div>
