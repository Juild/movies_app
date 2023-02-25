<script lang="ts">
	import { onMount } from 'svelte';

	let paragraph: HTMLElement;
	let weeks: object[] = [];
	let weeksInYear = 80 * 12 * 4;

    for (let i = 1; i < weeksInYear; i++) {
        weeks.push({ id: 'week' + i, content: 'Some content' });
    }

</script>
<div class="lifetime-grid">
    {#each weeks as { id, content }, i}
	    <div id={id} class="weeks"></div>
    {/each}
</div>
<style>
    .lifetime-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, 1em) ;
        padding: 2em;
        justify-content: center;

    }
    .weeks {
        /*  Background color not passed#08a4ff */
        background-color: #ee2e5d; /* Background color passed */
        width: 0.75em;
        height: 0.75em;
        border-radius: 89%;
        border-width: 0.05em;
        border-style: solid;
        transition: all 1s ease-out ;



    }
    .weeks:hover {
        transform: scale(5);
        border-color: #940b2d;
        background-color: rgb(255, 230, 0);
        transition: all 50ms ;
    }

</style>