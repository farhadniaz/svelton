<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    import StarSvg from './icons-svg/filled/star.svg';
    export let count = 5;
    export let color = "blue"
    export let value;
    let shadow = 0;
    const change = (index) => {
        value = index
        dispatch('change', value);

    }

</script>

<div class="svelton-rate" on:mouseleave={ ()=> shadow = 0}>
    {#each (Array(count).fill(1)) as item,index}
    <i 
    class={`${ ((shadow==0)? (value>=index+1): (shadow>=index+1)) ? "selected":""}`}
    on:mouseenter = { ()=> shadow = index + 1}
    on:click={()=>  change(index + 1)}>
        {@html StarSvg}
    </i>
    {/each}
</div>
<style type="text/sass">
    :global(svg){
        width: 25px;
    }
    i{
        cursor: pointer;
        margin-right: 2px;
        :global(svg *) {
            fill: #f0f0f0;
        }
    }
    .selected  :global(svg *) {
          fill:#fadd44;

    }

</style>