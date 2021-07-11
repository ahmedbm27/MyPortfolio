<script>
import { Router, Link, Route } from "svelte-routing";
import MyCV from "./routes/MyCV.svelte";
import Landing from "./routes/Landing.svelte";

  export let url = "";
</script>

<style>
  
</style>

<Router url="{url}">
    <Route path="/"><Landing /></Route>
	  <Route path="/mycv"><MyCV /></Route>
  </Router>