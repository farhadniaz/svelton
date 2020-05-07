<script>
    import Leaf from './leaf.svelte';

    export let icon;
    export let leafIcon;
    export let expanded = false;
    export let name;
    export let items;

    function toggle() {
        expanded = !expanded;
    }
</script>

<style>
    span {
        padding: 0 0 0 1.5em;

        background-size: 1em 1em;
        font-weight: bold;
        cursor: pointer;
    }

    ul {
        padding: 0.2em 0 0 0.5em;
        margin: 0 0 0 0.5em;
        list-style: none;
        border-left: 1px solid #eee;
    }

    li {
        padding: 0.2em 0;
    }
</style>

<span class:expanded on:click={toggle}><svelte:component this={icon}/> {name}</span>

{#if expanded}
	<ul>
		{#each items as item}
			<li>
		{#if item.type === 'root'}
    <svelte:self {...item}
    leafIcon={leafIcon}
    icon={icon}
    />
{:else}
	<Leaf {...item} icon={leafIcon}/>
{/if}
			</li>
		{/each}
	</ul>
{/if}