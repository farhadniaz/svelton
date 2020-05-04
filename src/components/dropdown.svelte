<script>
    import { onMount, createEventDispatcher } from 'svelte';

    import { createPopper } from '@popperjs/core';
    import clickOutside from './utils/click-outside.js';
    import downsvg from './icons-svg/outlined/down.svg';
    const dispatch = createEventDispatcher();
    export let trigger = "click";
    let show = false;
    let button, down, popper;

    const handelDown = () => {
        down.style.display = show ? 'block' : 'none';
        popper.update();
        dispatch('show', show);
    };
    const click = () => {
        if (trigger == "click") {
            show = !show;
            handelDown();
        }
    }
    const enter = () => {
        if (trigger == "hover") {
            show = true;
            handelDown();
        }
    }
    const leave = () => {
        if (trigger == "hover") {
            show = false;
            handelDown();
        }
    }
    const clickedOutside = () => {
        if (show) {
            show = false;
            handelDown();
        }
    }
    onMount(() => {
        down.style.minWidth = button.clientWidth + 'px';
        popper = createPopper(button, down, {
            placement: 'bottom',
        });
    });
</script>
<div class={`svelton-dropdown ${show?'show':''}`} on:mouseenter={enter} on:mouseleave={leave} use:clickOutside
    on:click_outside={clickedOutside}>
    <span class="svelton-dropdown__btn" bind:this={button} on:click={click}>

        <slot />
        {@html downsvg}
    </span>
    <div class="svelton-dropdown__down" bind:this={down} style="display: none;">
        <slot name="down" />
    </div>
</div>

<style type="text/sass">

    .svelton-dropdown{
        display: inline-block;
        &.show{
            .svelton-dropdown__btn :global(svg) {
transform: rotate(180deg);
 
    }

        }
    }
    .svelton-dropdown__btn{
        cursor: pointer;
        display: inline-block; 
    }

    .svelton-dropdown__btn :global(svg) {
height:15px;
width: 15px;

    transition: all 0.3s;
    }

.svelton-dropdown__down{
    z-index: 1;
    cursor: pointer;
    margin: 0;
    padding: 4px 0;
    text-align: left;
    list-style-type: none;
    background-color: #fff;
    background-clip: padding-box;
    border-radius: 2px;
    outline: none;
    box-shadow: 0 3px 6px -4px rgba(0,0,0,.12), 0 6px 16px 0 rgba(0,0,0,.08), 0 9px 28px 8px rgba(0,0,0,.05);
}
</style>