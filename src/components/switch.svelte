<script>
    let switched = false;
    const onClick = () => {
        switched = !switched;
    }

</script>
<button type="button" on:click={onClick} role="switch" 
aria-checked={switched} class={`svelton-switch ${switched?'svelton-switch-checked':""}`}
    svelton-click-animating={switched}>
    <span class="svelton-switch-inner">
        {#if switched }
        <slot name="checked"/>
        {:else}
        <slot name="unChecked"/>
        {/if}

    </span>
    <div class="svelton-click-animating-node"></div>
</button>

<style>
    .svelton-switch {
        margin: 0;
        padding: 0;
        color: rgba(0, 0, 0, .65);
        font-size: 14px;
        font-variant: tabular-nums;
        line-height: 1.5715;
        list-style: none;
        -webkit-font-feature-settings: 'tnum';
        font-feature-settings: 'tnum';
        position: relative;
        display: inline-block;
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
        min-width: 44px;
        height: 22px;
        line-height: 20px;
        vertical-align: middle;
        background-color: rgba(0, 0, 0, .25);
        border: 1px solid transparent;
        border-radius: 100px;
        cursor: pointer;
        -webkit-transition: all .36s;
        transition: all .36s;
        -webkit-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }

    .svelton-switch-inner {
        display: block;
        margin-right: 6px;
        margin-left: 24px;
        color: #fff;
        font-size: 12px;
    }


    [svelton-click-animating-without-extra-node=true]::after,
    .svelton-click-animating-node {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        display: block;
        border-radius: inherit;
        -webkit-box-shadow: 0 0 0 0 #1890ff;
        box-shadow: 0 0 0 0 #1890ff;
        -webkit-box-shadow: 0 0 0 0 var(--antd-wave-shadow-color);
        box-shadow: 0 0 0 0 var(--antd-wave-shadow-color);
        opacity: .2;
        -webkit-animation: fadeEffect 2s cubic-bezier(.08, .82, .17, 1), waveEffect .4s cubic-bezier(.08, .82, .17, 1);
        animation: fadeEffect 2s cubic-bezier(.08, .82, .17, 1), waveEffect .4s cubic-bezier(.08, .82, .17, 1);
        -webkit-animation-fill-mode: forwards;
        animation-fill-mode: forwards;
        content: '';
        pointer-events: none;
    }


    .svelton-switch-loading-icon,
    .svelton-switch::after {
        position: absolute;
        top: 1px;
        left: 1px;
        width: 18px;
        height: 18px;
        background-color: #fff;
        border-radius: 18px;
        cursor: pointer;
        -webkit-transition: all .36s cubic-bezier(.78, .14, .15, .86);
        transition: all .36s cubic-bezier(.78, .14, .15, .86);
        content: ' ';
    }

    .svelton-switch::after {
        -webkit-box-shadow: 0 2px 4px 0 rgba(0, 35, 11, .2);
        box-shadow: 0 2px 4px 0 rgba(0, 35, 11, .2);
    }



    .svelton-switch-checked::after {
        left: 100%;
        margin-left: -1px;
        -webkit-transform: translateX(-100%);
        transform: translateX(-100%);
    }
    .svelton-switch-checked {
    background-color: #1890ff;
}

.svelton-switch-checked .svelton-switch-inner {
    margin-right: 24px;
    margin-left: 6px;
}
</style>