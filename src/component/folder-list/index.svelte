<script>
    import File from './file.svelte';
    import FolderSVG from '../../icons-svg/outlined/folder.svg';
    export let expanded = false;
    export let name;
    export let files;

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

    .expanded {}

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

<span class:expanded on:click={toggle}>{@html FolderSVG} {name}</span>

{#if expanded}
	<ul>
		{#each files as file}
			<li>
		{#if file.type === 'folder'}
	<svelte:self {...file}/>
{:else}
	<File {...file}/>
{/if}
			</li>
		{/each}
	</ul>
{/if}