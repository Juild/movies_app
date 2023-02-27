<script lang="ts">
   
    export let age: string = '0';
    let weeks: object[] = [];
	let weeksInYear: number = 85 * 12 * 4;
    for (let i = 1; i < weeksInYear; i++) {
        weeks.push({id: i});
    }
    $:  weeksLived  = isNaN(parseInt(age) * 12 * 4) ? 0 : parseInt(age) * 12 * 4 ;


</script>
<div class="lifetime-grid">
    {#each weeks as weeks (weeks.id)}
	    <div class={weeks.id < weeksLived ? 'selected' : 'not-selected' }></div>
    {/each}
</div>
<style>
    .lifetime-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, 1em) ;
        padding: 2em;
        justify-content: center;

    }
    .not-selected, .selected {
        /*  Background color not passed#08a4ff */
        background-color: #ee2e5d; /* Background color passed */
        width: 0.75em;
        height: 0.75em;
        border-radius: 89%;
        border-width: 0.05em;
        border-style: solid;
        transition: all 1s ease-out ;
    }
    .selected {
        /*  Background color not passed#08a4ff */
        background-color: #deee2e; /* Background color passed */
    }
    .not-selected:hover, .selected:hover {
        transform: scale(5);
        border-color: #940b2d;
        background-color: rgb(255, 230, 0);
        transition: all 50ms ;
    }

</style>