<script>
    export let items=[];
    export let seprator="/";
</script>
<div class="svelton-breadcrumb">
    {#each items as Item, index}
        <span>
            <span class="svelton-breadcrumb-link">
        {#if typeof Item =="function" }
            <svelte:component this={Item}/>
        {:else if typeof Item =="object" }
        <a href={Item.href}>{Item.title}</a>
        {:else}
            {@html Item}
        {/if}
        </span>
        {#if items.length>index+1 }
        <span class="svelton-breadcrumb-separator">{seprator}</span>
        {/if}
    </span>
    {/each}

</div>

<style>
    .svelton-breadcrumb {
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    color: rgba(0,0,0,.65);
    font-variant: tabular-nums;
    line-height: 1.5715;
    list-style: none;
    -webkit-font-feature-settings: 'tnum';
    font-feature-settings: 'tnum';
    color: rgba(0,0,0,.45);
    font-size: 14px;
}
</style>