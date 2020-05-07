<script>
	import { Button, Drawer } from "../components";

	let visible = false;
	let visiblebottom = false;
	let visibleleft = false;
	let visibleright = false;



</script>

<section class="component-card">
	<h1>Drawer </h1>
	<p>some details </p>
	<Button on:click={()=>visible=!visible}>
		<span>drawer top</span>{" "}
	</Button>
	<Button on:click={()=>visiblebottom=!visiblebottom}>
		<span>drawer bottom</span>{" "}
	</Button>
	<Button on:click={()=>visibleleft=!visibleleft}>
		<span>drawer left</span>{" "}</Button>
	<Button on:click={()=>visibleright=!visibleright}><span>drawer right</span>{" "}</Button>


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




</section>