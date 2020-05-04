<script>
    import { createEventDispatcher } from 'svelte';
    import CloseSvg from './icons-svg/outlined/close.svg';

    const dispatch = createEventDispatcher();
    export let closable = false;
    let hidden = false;
    export let color;
    export let className = "";
    let isPreDefinedColor;
    const preDefinedColors = [
        "purple", "geekblue", "blue", "cyan", "green", "lime", "gold",
        "orange", "volcano", "red", "magenta"]

    $: isPreDefinedColor = preDefinedColors.indexOf(color) > -1;

    const close = () => {

        hidden = true;
        dispatch('close', hidden);
    }

</script>


<span class={` ${hidden? 'svelton-tag-hidden ' :''} ${className} svelton-tag ${(color &&
    isPreDefinedColor)?"svelton-tag-"+color:""}`} style={`${(color &&
    !isPreDefinedColor)?"background-color:"+color:""}`}>
    <slot />
    {#if closable}
<i class="anticon-close" on:click={close}>{@html CloseSvg}</i>
{/if}

</span>

<style type="text/sass">
    .svelton-tag {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        color: rgba(0,0,0,.65);
        font-size: 14px;
        font-variant: tabular-nums;
        line-height: 1.5715;
        list-style: none;
        font-feature-settings: 'tnum';
        display: inline-block;
        height: auto;
        margin-right: 8px;
        padding: 0 7px;
        font-size: 12px;
        line-height: 20px;
        white-space: nowrap;
        background: #fafafa;
        border: 1px solid #d9d9d9;
        border-radius: 2px;
        cursor: default;
        opacity: 1;
        transition: all .3s cubic-bezier(.78,.14,.15,.86);
    }
.svelton-tag .anticon-close :global(svg){
    display: inline-block;
    font-size: 10px;
    margin-left: 3px;
    color: rgba(0,0,0,.45);
    font-weight: 700;
    cursor: pointer;
    transition: all .3s cubic-bezier(.78,.14,.15,.86);
    vertical-align: middle;
    cursor: pointer;
    width: 1em;
    height: 1em;
    fill: currentcolor;
}




.svelton-tag-magenta {
    color: #eb2f96;
    background: #fff0f6;
    border-color: #ffadd2;
}
.svelton-tag-red {
    color: #f5222d;
    background: #fff1f0;
    border-color: #ffa39e;
}

.svelton-tag-volcano {
    color: #fa541c;
    background: #fff2e8;
    border-color: #ffbb96;
}
.svelton-tag-orange {
    color: #fa8c16;
    background: #fff7e6;
    border-color: #ffd591;
}

.svelton-tag-gold {
    color: #faad14;
    background: #fffbe6;
    border-color: #ffe58f;
}
.svelton-tag-lime {
    color: #a0d911;
    background: #fcffe6;
    border-color: #eaff8f;
}
.svelton-tag-green {
    color: #52c41a;
    background: #f6ffed;
    border-color: #b7eb8f;
}
.svelton-tag-cyan {
    color: #13c2c2;
    background: #e6fffb;
    border-color: #87e8de;
}
.svelton-tag-blue {
    color: #1890ff;
    background: #e6f7ff;
    border-color: #91d5ff;
}

.svelton-tag-geekblue {
    color: #2f54eb;
    background: #f0f5ff;
    border-color: #adc6ff;
}

.svelton-tag-purple {
    color: #722ed1;
    background: #f9f0ff;
    border-color: #d3adf7;
}


.svelton-tag-hidden {
    display: none;
}


</style>