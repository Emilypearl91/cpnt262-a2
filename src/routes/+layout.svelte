<script>
	import '../app.postcss';
	import {AppBar, AppShell} from '@skeletonlabs/skeleton';
	import Navbar from '../lib/components/navBar/Navbar.svelte';
	import Header from '../lib/components/header/Header.svelte';
	import Footer from '../lib/components/footer/Footer.svelte';

</script>



	
<AppShell>
	<svelte:fragment slot="header"><Navbar></Navbar></svelte:fragment>
	<!-- Router Slot -->
	<slot />
	<!-- ---- / ---- -->
	<svelte:fragment slot="pageFooter"><Footer></Footer></svelte:fragment>
</AppShell>

