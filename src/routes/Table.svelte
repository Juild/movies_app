<script lang="ts">
	import { onMount } from 'svelte';
    export let age: string = '0';
    let paragraph: HTMLElement;
    let weeks: object[] = [];
	$: weeks = [];
	let weeksInYear: number = 90 * 12 * 4;
    let weeksLived: number = parseInt(age) * 12 * 4;
    console.log(age)
    for (let i = 1; i < weeksInYear; i++) {
        if (i < weeksLived){
            weeks.push({ id: 'week', css_class: 'selected' });
        }else{
            weeks.push({ id: 'week', css_class: 'not-selected' });
        }
    }
    

</script>
<div class="lifetime-grid">
    {#each weeks as { id, css_class }, i}
	    <div id={id} class={css_class}></div>
    {/each}
</div>
<style>
    .lifetime-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, 1em) ;
        padding: 2em;
        justify-content: center;

    }
    #week {
        /*  Background color not passed#08a4ff */
        background-color: #ee2e5d; /* Background color passed */
        width: 0.75em;
        height: 0.75em;
        border-radius: 89%;
        border-width: 0.05em;
        border-style: solid;
        transition: all 1s ease-out ;
    }
    #week, .selected {
        background-color: green;
    }
    .week:hover {
        transform: scale(5);
        border-color: #940b2d;
        background-color: rgb(255, 230, 0);
        transition: all 50ms ;
    }

</style>