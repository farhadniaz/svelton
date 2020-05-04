<script>
    import { onMount, createEventDispatcher } from 'svelte';
    import { fade, fly } from 'svelte/transition'
    import Button from "./button.svelte"
    import CloseSVG from './icons-svg/outlined/close.svg';
    export let visible = false
    export let title = "title";
    export let type = "modal"; // confirm
    let mode = true;
    let dialogNode;
    let openTime;
    let origineAdded = false;
    let inTransition = false;
    let mousePosition = {};

    const dispatch = createEventDispatcher();

    const cancel = () => {
        close();
        dispatch('cancel')
    }
    const ok = () => {
        close();
        dispatch('ok')
    }

    const close = () => {


        // transition:fly
        mode = false;

        setTimeout(() => {
            visible = false;
            mode = true;
        }, 100);

    }


    const getClickPosition = (e) => {
        mousePosition = {
            x: e.pageX,
            y: e.pageY,
        };
    };



    const setTransformOrigin = (node, value) => {
        const style = node.style;
        ['Webkit', 'Moz', 'Ms', 'ms'].forEach((prefix) => {
            style[`${prefix}TransformOrigin`] = value;
        });
        style[`transformOrigin`] = value;
    }

    const getScroll = (w, top) => {
        let ret = w[`page${top ? 'Y' : 'X'}Offset`];
        const method = `scroll${top ? 'Top' : 'Left'}`;
        if (typeof ret !== 'number') {
            const d = w.document;
            ret = d.documentElement[method];
            if (typeof ret !== 'number') {
                ret = d.body[method];
            }
        }
        return ret;
    }
    const offset = (el) => {
        const rect = el.getBoundingClientRect();
        const pos = {
            left: rect.left,
            top: rect.top,
        };
        const doc = el.ownerDocument;
        const w = doc.defaultView || doc.parentWindow;
        pos.left += getScroll(w);
        pos.top += getScroll(w, true);
        return pos;
    }


    const onMaskClick = (e) => {
        // android trigger click on open (fastclick??)
        if (Date.now() - openTime < 300) {
            return;
        }
        if (e.target === e.currentTarget && !this.dialogMouseDown) {
            close(e);
        }
    }


    onMount(() => {

        // if (typeof window !== 'undefined' && window.document && window.document.documentElement) {} 
        window.addEventListener('click', getClickPosition);




        // else if (visible) {
        // inTransition = true;
        // if (mask && this.lastOutSideFocusNode && focusTriggerAfterClose) {
        //     try {
        //         this.lastOutSideFocusNode.focus();
        //     } catch (e) {
        //         this.lastOutSideFocusNode = null;
        //     }
        //     this.lastOutSideFocusNode = null;
        // }
        // }


    })



    $: if (visible && dialogNode) {
        // first show
        if (!origineAdded) {
            openTime = Date.now();
            // this.switchScrollingEffect();
            // this.tryFocus();
            if (mousePosition) {
                const elOffset = offset(dialogNode);
                debugger;
                // alert(`${mousePosition.x - elOffset.left}px ${mousePosition.y - elOffset.top}px`);
                setTransformOrigin(
                    dialogNode,
                    `${mousePosition.x - elOffset.left}px ${mousePosition.y - elOffset.top}px`,
                );
            } else {
                setTransformOrigin(dialogNode, '');
            }

            origineAdded = true;
        }
    }



</script>
{#if visible}
<div class="svelton-modal " 
transition:fade
on:click|self={close}

>
    <div
 

    class="svelton-modal__content  {mode ?'zoom-enter-active  zoom-enter':'zoom-leave-active  zoom-leave'} ">
        <div class="svelton-modal__content__header">
          <span class="svelton-modal__content__header__title">{title}</span>
            <i class="svelton-modal__content__header__close" on:click={close}>{@html CloseSVG}</i>
        </div>
        <div class="svelton-modal__content__body">
            body     <br/>
            dsfds
            <br/>
        
            lastOutSideFocusNodesdf     <br/>
            solid     <br/>
            <br/>
            lastOutSideFocusNodesfd
            <s>
                <br/>
            </s>
        </div>
        <div class="svelton-modal__content__footer">
           
            <Button on:click={ok} type="primary">Ok</Button> 
            <Button on:click={cancel}  danger >Cancel</Button>

    

        </div>
    </div>
</div>
{/if}

<style>

.svelton-modal__content__header {
    display: flex;
    justify-content: space-between;
}
.svelton-modal__content__header__close {
    cursor: pointer;
}
.svelton-modal__content__header__title {
    margin: auto 0;
}

    .svelton-modal {
        position: fixed;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 1000;
        height: 100%;
        background-color: rgba(0, 0, 0, .45);
        display: flex;
    }

    .svelton-modal__content {
        /* transform-origin: 525px 222px; */
        position: relative;
        background-color: #fff;
        background-clip: padding-box;
        border: 0;
        border-radius: 2px;
        -webkit-box-shadow: 0 3px 6px -4px rgba(0, 0, 0, .12), 0 6px 16px 0 rgba(0, 0, 0, .08), 0 9px 28px 8px rgba(0, 0, 0, .05);
        box-shadow: 0 3px 6px -4px rgba(0, 0, 0, .12), 0 6px 16px 0 rgba(0, 0, 0, .08), 0 9px 28px 8px rgba(0, 0, 0, .05);
        pointer-events: auto;
        margin: auto;
        min-width: 300px;
    }

    .svelton-modal__content__header {
        padding: 16px 24px;
        color: rgba(0, 0, 0, .65);
        background: #fff;
        border-bottom: 1px solid #f0f0f0;
        border-radius: 2px 2px 0 0;
    }

    .svelton-modal__content__body {
        padding: 24px;
        font-size: 14px;
        line-height: 1.5715;
        word-wrap: break-word;
    }

    .svelton-modal__content__footer {
        padding: 10px 16px;
        text-align: right;
        background: 0 0;
        border-top: 1px solid #f0f0f0;
        border-radius: 0 0 2px 2px;

        justify-content: space-between;
    display: flex;
    }

















    @keyframes NotificationFadeIn {
        0% {
            left: 0px;
            opacity: 0;
        }

        100% {
            left: 0;
            opacity: 1;
        }
    }



    @keyframes antZoomIn {
        0% {
            transform: scale(0.2);
            opacity: 0;
        }

        to {
            transform: scale(1);
            opacity: 1;
        }
    }


    .svelton-modal__content.zoom-enter {
        -webkit-transform: none;
        transform: none;
        opacity: 0;
        -webkit-animation-duration: .3s;
        animation-duration: .3s;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }


    .svelton-modal__content.zoom-enter-active {
        -webkit-animation-name: antZoomIn;
        animation-name: antZoomIn;
        -webkit-animation-play-state: running;
        animation-play-state: running;
        opacity: 1;
    }




    @keyframes antZoomOut {
  0% {
    transform: scale(1);
  }
  to {
    transform: scale(0.2);
    opacity: 0;
  }
}




  .zoom-leave {
  animation-duration: 0.2s;
  animation-fill-mode: both;
  animation-play-state: paused;
}

.zoom-leave.zoom-leave-active {
  animation-name: antZoomOut;
  animation-play-state: running;
  pointer-events: none;
}




</style>