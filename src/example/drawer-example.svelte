<script>
	import Highlighter from '../example/sectioner/highlighter.svelte'
	import Sectioner from './sectioner/index.svelte';
	import { Button, Drawer } from "../components";

	let visible = false;
	let visiblebottom = false;
	let visibleleft = false;
	let visibleright = false;
	let visiblebackdropClosableRight = false;
	let usageTop = `
import { Drawer, Button } from 'svelton';
let visible = false;
<Button on:click={()=>visible=!visible}>
	Click me to open top Drawer
</Button>
<Drawer bind:visible={visible} placement="top">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
    `;


	let usageRight = `
import { Drawer, Button } from 'svelton';
let visible = false;
<Button on:click={()=>visible=!visible}>
	Click me to open right Drawer
</Button>
<Drawer bind:visible={visible} placement="right">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
	`;

	let usageLeft = `
import { Drawer, Button } from 'svelton';
let visible = false;
<Button on:click={()=>visible=!visible}>
	Click me to open left Drawer
</Button>
<Drawer bind:visible={visible} placement="left">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
	`;
	let usageBottom = `
import { Drawer, Button } from 'svelton';
let visible = false;
<Button on:click={()=>visible=!visible}>
	Click me to open bottom Drawer
</Button>
<Drawer bind:visible={visible} placement="bottom">
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
	`;
	let usagebackdropClosable = `
import { Drawer, Button } from 'svelton';
let visible = false;
<Button on:click={()=>visible=!visible}>
Click me to open right Drawer; no backdrop close
</Button>
<Drawer bind:visible={visible} 
backdropClosable={false}>
	<p>Some contents...</p>
	<p>Some contents...</p>
	<p>Some contents...</p>
</Drawer>
	`;










	let api = {
		properties: [
			{
				name: "visible",
				description: "visible the drawer",
				type: "boolean",
				default: "false"
			},
			{
				name: "backdropClosable",
				description: "indicates close the drawer when clicking on backdrop",
				type: "boolean",
				default: "true"
			},
			{
				name: "placement",
				description: "set the placement of drawer, values top | right | bottom | left",
				type: "string",
				default: "right"
			}
		],
		events: [{
			name: "open",
			description: "will be trigger whenever the drawer opend "
		}, {
			name: "close",
			description: "will be trigger whenever the drawer closed "
		}],
		methods: []
	}

</script>
<Sectioner title="Drawer" api={api}>
	<span slot="usage">
		<Highlighter>
			{usageTop}
		</Highlighter>
	</span>

	<div slot="examples">
		<div class="example-item">
			<Button on:click={()=>visible=!visible}>
				Click me to open top Drawer
			</Button>
			<Drawer bind:visible={visible} placement="top">
				<p>Some contents...</p>
				<p>Some contents...</p>
				<p>Some contents...</p>
			</Drawer>
		</div>



		<div class="example-item">
			<Highlighter>
				{usagebackdropClosable}
			</Highlighter>
			<Button on:click={()=>visiblebackdropClosableRight=!visiblebackdropClosableRight}>
				Click me to open right Drawer; no backdrop close
			</Button>
			<Drawer bind:visible={visiblebackdropClosableRight} backdropClosable={false}>
				<p>Some contents...</p>
				<p>Some contents...</p>
				<p>Some contents...</p>
			</Drawer>
		</div>
		<div class="example-item">
			<Highlighter>
				{usageRight}
			</Highlighter>
			<Button on:click={()=>visibleright=!visibleright}>
				Click me to open right Drawer
			</Button>
			<Drawer bind:visible={visibleright}>
				<p>Some contents...</p>
				<p>Some contents...</p>
				<p>Some contents...</p>
			</Drawer>
		</div>
		<div class="example-item">
			<Highlighter>
				{usageLeft}
			</Highlighter>
			<Drawer bind:visible={visibleleft} placement="left">
				<p>Some contents...</p>
				<p>Some contents...</p>
				<p>Some contents...</p>
			</Drawer>
			<Button on:click={()=>visibleleft=!visibleleft}>
				Click me to open left Drawer</Button>
		</div>


		<div class="example-item">
			<Highlighter>
				{usageBottom}
			</Highlighter>
			<Drawer bind:visible={visiblebottom} placement="bottom">
				<p>Some contents...</p>
				<p>Some contents...</p>
				<p>Some contents...</p>
			</Drawer>
			<Button on:click={()=>visiblebottom=!visiblebottom}>

				Click me to open bottom Drawer

			</Button>
		</div>

	</div>
</Sectioner>