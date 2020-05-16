<script>
    export let items = [];
    export let seprator = "/";

    // {#if typeof Item =="function" }
    //         <svelte:component this={Item}/> 
</script>
<div class="svelton-breadcrumb">
    {#each items as Item, index}
        <span>
            <span class="svelton-breadcrumb-link">

        {#if typeof Item =="object" }
        <a href={Item.href} on:click={Item.onClick} >{Item.title}</a>
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

<style type="text/sass">
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
    :global(a){
        text-decoration: none;
        }
}

</style>