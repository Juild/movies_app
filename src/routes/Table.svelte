<script lang="ts">
	import { onMount } from 'svelte';

	let paragraph: HTMLElement;
	let weeks: object[] = [];
	let weeksInYear = 80 * 12 * 4;

    for (let i = 1; i < weeksInYear; i++) {
        console.log(i);
        weeks.push({ id: 'week' + i, content: 'Some content' });
    }
    console.log(weeks);

	onMount(() => (paragraph.textContent = 'This is a programatically generated paragraph'));
</script>

<div class="lifetime-grid">
    {#each weeks as { id, content }, i}
	    <div {id}, class="weeks"></div>
    {/each}
</div>

<style>
    .lifetime-grid {
        /* height: 1000cap;
        width: 1000cap; */
        /* position: relative;
        top: 30px;
        bottom: 30px;
        left: 10px;
        right: 30px; */
        display: grid;
        grid-template-columns: repeat(100, 0.1em) ;
        grid-gap: 0.5em;
        text-align: inherit;
        /* padding: ; */
    }
    .weeks {
        background-color: aqua;
        width: 0.4em;
        height: 0.4em;
        border-radius: 10%;
        border-color: blue;
        border-style: solid;
        border-width: 0.07em;
    }
</style>