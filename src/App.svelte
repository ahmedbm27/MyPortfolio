<script>
import { Router, Link, Route } from "svelte-routing";
  import MyCV from "./routes/MyCV.svelte";
  

  export let url = "";
</script>


<Router url="{url}">
	  <Route path="/"><MyCV /></Route>
  </Router>