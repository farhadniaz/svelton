<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();


    import CloseSVG from './icons-svg/outlined/close.svg';
    export let title;
    export let description;
    export let closeable = true;
    export let type = "warning"; // success, info, warning, error
    const typeClassName = `svelton-alert-${type}`;
    $: visible = true;
    const close = () => {
        visible = false;
        dispatch('close');
    }
</script>

{#if visible}
<div data-show="true" class={`svelton-alert ${typeClassName}`}>
    <span class="svelton-alert-message">{title}</span>
    <span class="svelton-alert-description">{description}</span>
    {#if closeable}
    <i class="svelton-alert-close" on:click={close}>
        {@html CloseSVG}
    </i>
    {/if}
</div>
{/if}
<style>
    .svelton-alert-close {
        cursor: pointer;
        height: 16px;
        width: 16px;
        position: absolute;
        top: 6px;
        right: 6px;
    }

    .svelton-alert {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        color: rgba(0, 0, 0, .65);
        font-size: 14px;
        line-height: 1.5715;
        list-style: none;
        -webkit-font-feature-settings: 'tnum';
        font-feature-settings: 'tnum';
        position: relative;
        padding: 16px;
        word-wrap: break-word;
        border-radius: 2px;
    }


    .svelton-alert-error {
        background-color: #fff2f0;
        border: 1px solid #ffccc7;
    }


    .svelton-alert-warning {
        background-color: #fffbe6;
        border: 1px solid #ffe58f;
    }

    .svelton-alert-info {
        background-color: #e6f7ff;
        border: 1px solid #91d5ff;
    }

    .svelton-alert-success {
        background-color: #f6ffed;
        border: 1px solid #b7eb8f;
    }

    .svelton-alert-message {
        display: block;
        margin-bottom: 4px;
        color: rgba(0, 0, 0, .85);
        font-size: 16px;
    }

    .svelton-alert-description {
        display: block;
        font-size: 14px;
        line-height: 22px;
    }
</style>