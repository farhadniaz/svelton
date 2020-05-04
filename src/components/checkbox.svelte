<script>
</script>

<label class="svelton-checkbox-wrapper">
    <span class="svelton-checkbox">
        <slot name="input" />
        <span class="svelton-checkbox-inner"></span>
    </span>
    <span><slot /></span>
</label>

<style type="text/sass">
  .svelton-checkbox-wrapper :global(input){
    display: none;
}
    .svelton-checkbox-wrapper {
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        color: rgba(0, 0, 0, .65);
        font-size: 14px;
        font-variant: tabular-nums;
        line-height: 1.5715;
        list-style: none;
        -webkit-font-feature-settings: 'tnum';
        font-feature-settings: 'tnum';
        display: inline-block;
        line-height: unset;
        cursor: pointer;
    }

    .svelton-checkbox {
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
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
        top: -.09em;
        display: inline-block;
        line-height: 1;
        white-space: nowrap;
        vertical-align: middle;
        outline: none;
        cursor: pointer;
    }

    .svelton-checkbox+span {
        padding-right: 8px;
        padding-left: 8px;
    }

    .svelton-checkbox-input {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 1;
        width: 100%;
        height: 100%;
        cursor: pointer;
        opacity: 0;
    }


    .svelton-checkbox-inner::after {
        position: absolute;
        top: 50%;
        left: 22%;
        display: table;
        width: 5.71428571px;
        height: 9.14285714px;
        border: 2px solid #fff;
        border-top: 0;
        border-left: 0;
        -webkit-transform: rotate(45deg) scale(0) translate(-50%, -50%);
        transform: rotate(45deg) scale(0) translate(-50%, -50%);
        opacity: 0;
        -webkit-transition: all .1s cubic-bezier(.71, -.46, .88, .6), opacity .1s;
        transition: all .1s cubic-bezier(.71, -.46, .88, .6), opacity .1s;
        content: ' ';
    }

    .svelton-checkbox-inner {
        position: relative;
        top: 0;
        left: 0;
        display: block;
        width: 16px;
        height: 16px;
        direction: ltr;
        background-color: #fff;
        border: 1px solid #d9d9d9;
        border-radius: 2px;
        border-collapse: separate;
        -webkit-transition: all .3s;
        transition: all .3s;
    }

    
    :global( .svelton-checkbox-checked::after) {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        border: 1px solid #1890ff;
        border-radius: 2px;
        visibility: hidden;
        -webkit-animation: antCheckboxEffect .36s ease-in-out;
        animation: antCheckboxEffect .36s ease-in-out;
        -webkit-animation-fill-mode: backwards;
        animation-fill-mode: backwards;
        content: '';
    }

    :global([type="checkbox"]:checked + .svelton-checkbox-inner){
        background-color: #1890ff;
        border-color: #1890ff;
    }

    :global([type="checkbox"]:checked + .svelton-checkbox-inner::after) {
        position: absolute;
        display: table;
        border: 2px solid #fff;
        border-top: 0;
        border-left: 0;
        -webkit-transform: rotate(45deg) scale(1) translate(-50%, -50%);
        transform: rotate(45deg) scale(1) translate(-50%, -50%);
        opacity: 1;
        -webkit-transition: all .2s cubic-bezier(.12, .4, .29, 1.46) .1s;
        transition: all .2s cubic-bezier(.12, .4, .29, 1.46) .1s;
        content: ' ';
    }

    input[type=radio],
    input[type=checkbox] {
        -webkit-box-sizing: border-box;
        box-sizing: border-box;
        padding: 0;
    }
</style>