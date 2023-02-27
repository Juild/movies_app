<script lang="ts">
	import Table from "./Table.svelte";
    let age: string;
</script>
<h1>The Tail End</h1>
<h2>How many weeks do you have left?</h2>
<input bind:value={age}  placeholder="Input your age"/>
<p id="disclaimer">(Each ball represents a week. The number of weeks is approximated by calculating 90 years, 12 months per year, 4 weeks per month.)</p>
<Table age={age}></Table>
<style>
    h1, h2, p {
        color: white;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    h1 {
        font-size: 36pt;
    }
    input {
        border-radius: 1cm;
        padding: 0.5em;
    }
    #disclaimer {
        font-size: small;
    }
</style>