<script lang="ts">
	import { Router, Route } from "svelte-routing";
	import Home from './home/Home.svelte';
import Navbar from "./home/Navbar.svelte";
	import Paintings from "./paintings/Paintings.svelte";
	export let url = "";
</script>


<Router url={url}>
	<Navbar/>		  
	<Route path="paintings"><Paintings /></Route>
	<Route path="/"><Home /></Route>
</Router>

