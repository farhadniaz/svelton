<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    export let selected;
    export let value;
    export let group;
    const onChange = () => {
        dispatch("change", value);
    }
    let cheked = false;
    $: if (group) {
        cheked = group == value
    }
    $: if (selected) {
        cheked = selected != undefined;
    }
</script>
<label class="svelton-radio-wrapper">
    <span class={`svelton-radio ${cheked?'svelton-radio-checked':''}`}>
        <slot name="input" />
        <span class="svelton-radio-inner"></span>
    </span>  
    <span><slot /></span>
</label>
<style>

.svelton-radio-wrapper :global(input){
display: none;
}
    .svelton-radio-wrapper {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        color: rgba(0, 0, 0, .65);
        font-size: 14px;
        font-variant: tabular-nums;
        line-height: 1.5715;
        list-style: none;
        font-feature-settings: 'tnum';
        position: relative;
        display: inline-block;
        margin-right: 8px;
        white-space: nowrap;
        cursor: pointer;
    }

    .svelton-radio {

        box-sizing: border-box;
        margin: 0;
        padding: 0;
        color: rgba(0, 0, 0, .65);
        font-size: 14px;
        font-variant: tabular-nums;
        line-height: 1.5715;
        list-style: none;
        font-feature-settings: 'tnum';
        position: relative;
        display: inline-block;
        line-height: 1;
        white-space: nowrap;
        vertical-align: sub;
        outline: none;
        cursor: pointer;
    }


    .svelton-radio-input {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 1;
        cursor: pointer;
        opacity: 0;
    }

    input[type=radio] {
        box-sizing: border-box;
        padding: 0;
    }

    .svelton-radio-inner {
        position: relative;
        top: 0;
        left: 0;
        display: block;
        width: 16px;
        height: 16px;
        background-color: #fff;
        border-color: #d9d9d9;
        border-style: solid;
        border-width: 1px;
        border-radius: 100px;

        transition: all .3s;
        box-sizing: border-box;
    }

    .svelton-radio-checked::after {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border: 1px solid #1890ff;
        border-radius: 50%;
        visibility: hidden;

        animation: sveltonRadioEffect .36s ease-in-out;

        animation-fill-mode: both;
        content: '';
    }

    .svelton-radio-inner::after {
        position: absolute;
        top: 3px;
        left: 3px;
        display: table;
        width: 8px;
        height: 8px;
        background-color: #1890ff;
        border-top: 0;
        border-left: 0;
        border-radius: 8px;

        transform: scale(0);
        opacity: 0;

        transition: all .3s cubic-bezier(.78, .14, .15, .86);
        content: ' ';
    }

    [type="radio"]:checked +  .svelton-radio-inner {
        border-color: #1890ff;
    }

    [type="radio"]:checked + .svelton-radio-inner::after {

        transform: scale(1);
        opacity: 1;

        transition: all .3s cubic-bezier(.78, .14, .15, .86);
    }
</style>