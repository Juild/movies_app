<script lang="ts">
	import Table from "./Table.svelte";
    let movies: string = "";
</script>
<h1>Welcome to Your Lifetime</h1>
<p>Search for a day</p>
<input bind:value={movies}  placeholder="Search for any movie you want here!"/>
<Table></Table>
