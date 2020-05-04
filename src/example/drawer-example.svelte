<script>
	import { Button, Drawer } from "../components";
	
	let visible = false;
	let visiblebottom = false;
	let visibleleft = false;
	let visibleright = false;



</script>

<Button on:click={()=>visible=true}>
	<span>drawer top</span>{" "}
</Button>
<Button on:click={()=>visiblebottom=true}>
	<span>drawer bottom</span>{" "}
</Button>
<Button on:click={()=>visibleleft=true}>
	<span>drawer left</span>{" "}</Button>
<Button on:click={()=>visibleright=true}><span>drawer right</span>{" "}</Button>


<Drawer bind:visible={visible} placement="top">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>

<Drawer bind:visible={visibleright}>
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>

<Drawer bind:visible={visibleleft} placement="left">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
<Drawer bind:visible={visiblebottom} placement="bottom">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>