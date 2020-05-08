<script>
    import { fade, fly } from 'svelte/transition'
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    import CloseSVG from './icons-svg/outlined/close.svg';

    export let placement = "right"; //	The placement of the Drawer.	top | right | bottom | left	 
    export let visible = false;
    export let title = "title";
    export let backdropClosable = true;

    let drawerClientWidth;
    let drawerClientHeight;
    $: transitionFly = { x: drawerClientWidth, duration: 350 };
    // { x: -drawerClientWidth,  duration: 350 }
    const close = () => {
        visible = false;
        dispatch('close', visible);
    }

    $: if (visible) {
        dispatch('open', visible);
    } else {
    }


    const closeWithBackdrop = () => {
        debugger;
        if (backdropClosable) {
            debugger;
            close();
        }
    }
</script>


{#if visible}
<div class="svelton-drawer svelton-drawer-{placement}"
on:click|self={closeWithBackdrop} transition:fade>
{#if visible}

    <div class="svelton-drawer-content-wrapper" 
    transition:fly="{{ [(placement=='left'||placement=='right'?'x':'y')]: (placement=='left'||placement=='top'? -drawerClientWidth:drawerClientWidth),  duration: 350}}">
     
        <div class="svelton-drawer-content" >
            <div class="svelton-drawer-wrapper-body">
                <div class="svelton-drawer-header">
                    <div class="svelton-drawer-title">{title}</div>
                    <i class="svelton-drawer-header__close" on:click={close}>{@html CloseSVG}</i>
                </div>
                <div class="svelton-drawer-body"  bind:clientWidth={drawerClientWidth}
                bind:clientHeight={drawerClientHeight}>
                    <slot />
                </div>
            </div>
        </div>
    </div>
    {/if}
</div>
{/if}

<style type="text/sass">
    .svelton-drawer {
    position: fixed;
    width: 100vw;
    height: 100vh;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0,0,0,.45);
    transition: height 0s ease .3s,width 0s ease .3s,-webkit-transform .3s cubic-bezier(.7,.3,.1,1);
    transition: transform .3s cubic-bezier(.7,.3,.1,1),height 0s ease .3s,width 0s ease .3s;
    transition: transform .3s cubic-bezier(.7,.3,.1,1),height 0s ease .3s,width 0s ease .3s,-webkit-transform .3s cubic-bezier(.7,.3,.1,1);
}
.svelton-drawer{
    display: flex;
    z-index: 1000;
    opacity: 1;
}

.svelton-drawer-header__close :global(svg){
    height: 16px;
    cursor: pointer;
}
.svelton-drawer-content {
    position: relative;
    z-index: 1;
    overflow: auto;
    background-color: #fff;
    background-clip: padding-box;
    border: 0;
    
}



.svelton-drawer-content-wrapper{
    min-width: 250px;
}

.svelton-drawer.svelton-drawer-top .svelton-drawer-content ,
.svelton-drawer.svelton-drawer-bottom .svelton-drawer-content{
 
    width: 100vw;
}

.svelton-drawer.svelton-drawer-top .svelton-drawer-content-wrapper {
margin-top: 0;
    margin-bottom: auto;
}
.svelton-drawer .svelton-drawer-content-wrapper{
    transition: all 0.3s;
}

.svelton-drawer.svelton-drawer-bottom  .svelton-drawer-content-wrapper{
    margin-bottom: 0;
    margin-top: auto;
}

.svelton-drawer.svelton-drawer-right .svelton-drawer-content-wrapper{
    margin-right: 0;
    margin-left: auto;
}
.svelton-drawer.svelton-drawer-left ,
.svelton-drawer.svelton-drawer-right{
    height: 100vh;
}
.svelton-drawer.svelton-drawer-left  .svelton-drawer-content,
.svelton-drawer.svelton-drawer-right .svelton-drawer-content{
    height: 100vw;
}

.svelton-drawer.svelton-drawer-left .svelton-drawer-content-wrapper{
    margin-left: 0;
    margin-right: auto;
}




.svelton-drawer-wrapper-body {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -ms-flex-wrap: nowrap;
    flex-wrap: nowrap;
    width: 100%;
    height: 100%;
}

.svelton-drawer-header {
    position: relative;
    padding: 16px 24px;
    color: rgba(0,0,0,.65);
    background: #fff;
    border-bottom: 1px solid #f0f0f0;
    border-radius: 2px 2px 0 0;
    display: flex;
}
.svelton-drawer-title {
    margin: 0;
    color: rgba(0,0,0,.85);
    font-weight: 500;
    font-size: 16px;
    line-height: 22px;
    width: 100%;
}

.svelton-drawer-body {
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
    padding: 24px;
    overflow: auto;
    font-size: 14px;
    line-height: 1.5715;
    word-wrap: break-word;
}

</style>