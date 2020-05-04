<script>
    export let title;
    export let description;
export let type="warning"; // success, info, warning, error
const typeClassName=`svelton-alert-${type}`;

import SG from './icons-svg/filled/account-book.svg';



</script>


<div data-show="true" class={`svelton-alert ${typeClassName}`}>
    <span class="svelton-alert-message">{title}</span>
    <span class="svelton-alert-description">{description}</span>
    </div>
<style>

.svelton-alert {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    color: rgba(0,0,0,.65);
    font-size: 14px;
    line-height: 1.5715;
    list-style: none;
    -webkit-font-feature-settings: 'tnum';
    font-feature-settings: 'tnum';
    position: relative;
    padding:16px;
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
    color: rgba(0,0,0,.85);
    font-size: 16px;
}
.svelton-alert-description {
    display: block;
    font-size: 14px;
    line-height: 22px;
}


</style>