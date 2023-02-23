<script lang="ts">
	import Table from "./Table.svelte";
    let movies: string = "";
</script>
<h1>The Tail End</h1>
<p>How many weeks do you have left?</p>
<input bind:value={movies}  placeholder="Input your age"/>
<Table ></Table>
<style>
    h1, p {
        color: white;
    }
    input {
        border-radius: 1cm;
        padding: 0.5em;
    }

</style>