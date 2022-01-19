<script>
	import router from "page";
	import Nav from "./components/layout/Nav.svelte";
	import Home from "./pages/Home/Home.svelte";
	import Homes from "./pages/Home/Homes.svelte";
	import TopMaintenanceHomes from "./pages/Home/TopMaintenanceHomes.svelte";
	import Complaints from "./pages/Complaint/Complaints.svelte";
	import ComplaintFrequency from "./pages/Complaint/ComplaintFrequency.svelte";
	import WaitingList from "./pages/Client/WaitingList.svelte";
	import WaitingListQualified from "./pages/Client/WaitingListQualified.svelte";

	let page;

	router('/', () => page = Home);
	router('/homes', () => page = Homes);
	router('/homes/top-maintenance', () => page = TopMaintenanceHomes);
	router('/complaints', () => page = Complaints);
	router('/complaints/complaint-frequency', () => page = ComplaintFrequency);
	router('/waiting-list', () => page = WaitingList);
	router('/waiting-list/qualified', () => page = WaitingListQualified);

	router.start();
</script>

<svelte:head>
	<title>Housing association web UI</title>
	<link rel="stylesheet" href="/css/main.css">
	<link rel="stylesheet" href="/fontawesome/css/all.css">
	<script src="/js/bootstrap.min.js" defer></script>
</svelte:head>

<Nav/>

<main class="bg-light py-5 min-vh-100">
	<section class="container py-5 px-2 px-md-5 mt-5 bg-white rounded shadow-sm">
		<svelte:component this="{page}"/>
	</section>
</main>
