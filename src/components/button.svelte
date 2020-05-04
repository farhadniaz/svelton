<script>
	export let danger=false;
	export let type="default";	// dashed primary link default
	let className=type!="default"?`svelton-btn-${type}`:"";
	className+=danger ? "svelton-btn-dangerous":"";
</script>


	<button on:click type="button" class={`svelton-btn ${className}`} >
		<span><slot>{type}</slot></span>
	</button>


<style>

.svelton-btn {
    margin:0;
    line-height: 1.5715;
    position: relative;
    display: inline-block;
    font-weight: 400;
    white-space: nowrap;
    text-align: center;
    background-image: none;
    border: 1px solid transparent;
    -webkit-box-shadow: 0 2px 0 rgba(0,0,0,.015);
    box-shadow: 0 2px 0 rgba(0,0,0,.015);
    cursor: pointer;
    -webkit-transition: all .3s cubic-bezier(.645,.045,.355,1);
    transition: all .3s cubic-bezier(.645,.045,.355,1);
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    -ms-touch-action: manipulation;
    touch-action: manipulation;
    height: 32px;
    padding: 4px 15px;
    font-size: 14px;
    border-radius: 2px;
    color: rgba(0,0,0,.65);
    background-color: #fff;
    border-color: #d9d9d9;
}


.svelton-btn-primary {
    color: #fff;
    background-color: #1890ff;
    border-color: #1890ff;
    text-shadow: 0 -1px 0 rgba(0,0,0,.12);
    -webkit-box-shadow: 0 2px 0 rgba(0,0,0,.045);
    box-shadow: 0 2px 0 rgba(0,0,0,.045);
}
.svelton-btn-dashed {
    color: rgba(0,0,0,.65);
    background-color: #fff;
    border-color: #d9d9d9;
    border-style: dashed;
}

.svelton-btn-link {
    color: #1890ff;
    background-color: transparent;
    border-color: transparent;
    -webkit-box-shadow: none;
    box-shadow: none;
}

.svelton-btn-dangerous {
    color: #fff;
    background-color: #ff4d4f;
    border-color: #ff4d4f;
    text-shadow: 0 -1px 0 rgba(0,0,0,.12);
    -webkit-box-shadow: 0 2px 0 rgba(0,0,0,.045);
    box-shadow: 0 2px 0 rgba(0,0,0,.045);
}
.svelton-btn, .svelton-btn:active, .svelton-btn:focus {
    outline: 0;
}


.svelton-btn:hover, .svelton-btn:focus, .svelton-btn:active, .svelton-btn.active {
    text-decoration: none;
    background: #fff;
}

.svelton-btn-primary:hover, 
.svelton-btn-primary:focus {
    color: #fff;
    background-color: #40a9ff;
    border-color: #40a9ff;
}

.svelton-btn-dangerous:hover, 
.svelton-btn-dangerous:focus {
	color: #fff;
    background-color: #ff7875;
    border-color: #ff7875;
}



</style>