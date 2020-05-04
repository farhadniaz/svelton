<script>
	import Header from './header.svelte';

	// components
	import Fileupload from "./component/fileupload.svelte"
	import Button from "./component/button.svelte"
	import Breadcrumb from "./component/breadcrumb.svelte"
	import Alert from "./component/alert.svelte"
	import Dropdown from "./component/dropdown.svelte"
	import Switch from "./component/switch.svelte"
	import Rate from "./component/rate.svelte"
	import Pagination from "./component/pagination.svelte"
	import Tag from "./component/tag.svelte"
	import Checkbox from "./component/checkbox.svelte"
	import Radio from "./component/radio.svelte"
	import RangeSliderExmple from './range-slider-exmple.svelte'
	import DrawerExample from './drawer-example.svelte'
	import FolderExample from './folder-example.svelte';
	import Modal from "./component/modal.svelte"

	let modalVisible = false;
	let group = null;
	const groupChanges = ({ detail }) => group = detail;
	let singleCheckBox = "";
	let groupCheckBox = [];
	let radiodata = "";
	let radiodataGroup = [];





</script>

<Header />


<section class="content-section">
	<aside>
		<ul>
			<li>
				<Button type="link">
					Fileupload
				</Button>
			</li>
			<li>
				<Button type="link">
					Modal
				</Button>
			</li>
			<li>
				<Button type="link">
					Drawer
				</Button>
			</li>
			<li>
				<Button type="link">
					Tree
				</Button>
			</li>
			<li>
				<Button type="link">
					Range Slider
				</Button>
			</li>
			<li>
				<Button type="link">
					Radio
				</Button>
			</li>
			<li>
				<Button type="link">
					Checkbox
				</Button>
			</li>
			<li>
				<Button type="link">
					switch
				</Button>
			</li>
			<li>
				<Button type="link">
					Button
				</Button>
			</li>
			<li>
				<Button type="link">
					Dropdown
				</Button>
			</li>
			<li>
				<Button type="link">
					Pagination
				</Button>
			</li>
			<li>
				<Button type="link">
					Breadcrumb
				</Button>
			</li>
			<li>
				<Button type="link">
					Rate
				</Button>
			</li>
			<li>
				<Button type="link">
					Alert
				</Button>
			</li>
		</ul>
	</aside>
	<main>

		<section class="component-card">
			<h1>Fileupload</h1>
			<p>some details </p>
			<Fileupload />
		</section>

		<section class="component-card">
			<h1>Modal</h1>
			<p>some details </p>
			<Modal bind:visible={modalVisible} title="my title" on:ok={()=>{alert("ok")}}
				on:cancel={()=>{alert("cancel")}}
				/>
				<Button on:click={()=>modalVisible=!modalVisible}>modalVisible</Button>
		</section>



		<section class="component-card">
			<h1>Drawer </h1>
			<p>some details </p>
			<DrawerExample />
		</section>

		<section class="component-card">
			<h1>Tree</h1>
			<p>some details </p>
			<FolderExample />
		</section>



		<section class="component-card">
			<h1>Range Slider </h1>
			<p>some details </p>
			<RangeSliderExmple />
		</section>


		<section class="component-card">
			<h1>Input </h1>
			<p>some details </p>
			<input type=text placeholder="sfsdfd" />
		</section>


		<section class="component-card">
			<h1>Radio </h1>
			<p>some details </p>
			{radiodata}

			<Radio>
				sdfsdfdsf
				<input type="radio" bind:group={radiodata} value="single" slot="input" />

			</Radio>
			<br />
			<Radio>
				a
				<input type="radio" bind:group={radiodataGroup} value="a" slot="input" />

			</Radio>
			<Radio>
				<input type="radio" bind:group={radiodataGroup} value="b" slot="input" />
			</Radio>
			{radiodataGroup}
		</section>


		<section class="component-card">
			<h1>Checkbox </h1>
			<p>some details </p>
			<Checkbox>value singleCheckBox
				<input type="checkbox" bind:group={singleCheckBox} value="single" slot="input">
			</Checkbox>
			{singleCheckBox}
			<Checkbox>group Checkbox
				<input type="checkbox" bind:group={groupCheckBox} value="Rice" slot="input">
			</Checkbox>
			<Checkbox>group Checkbox
				<input type="checkbox" bind:group={groupCheckBox} value="gop" slot="input">
			</Checkbox>
			<!-- <Checkbox  group={groupCheckBox} value="2">Checkbox</Checkbox> -->
			<!-- <Checkbox  group={groupCheckBox} value="3">Checkbox</Checkbox> -->
			<!-- <Checkbox>Checkbox</Checkbox> -->
			{groupCheckBox}
		</section>


		<section class="component-card">
			<h1>Tag </h1>
			<p>some details </p>
			<Tag>one</Tag>
			<Tag closable>farhad</Tag>
			<Tag color="magenta" closable>magenta</Tag>
			<Tag color="red" closable on:close={({detail})=>{alert(detail)}}>red</Tag>
			<Tag color="volcano" closable>volcano</Tag>
			<Tag color="orange" closable>orange</Tag>
			<Tag color="gold" closable>gold</Tag>
			<Tag color="black" closable>black</Tag>
			<Tag color="lime" closable>lime</Tag>
			<Tag color="green" closable>green</Tag>
			<Tag color="cyan" closable>cyan</Tag>
			<Tag color="blue" closable>blue</Tag>
			<Tag color="geekblue" closable>geekblue</Tag>
			<Tag color="purple" closable className="sdfsdfds">purple</Tag>

		</section>


		<section class="component-card">
			<h1>Pagination </h1>
			<p>some details </p>

			<Pagination />
			<br />
			<Pagination total={1000} currentPage={10} perPage={10} range={10} />

		</section>

		<section class="component-card">
			<h1>Rate </h1>
			<p>some details </p>
			<Rate />
			<br />
			<Rate value={3} count={6} />
		</section>

		<section class="component-card">
			<h1>Switch </h1>
			<p>some details </p>
			<Switch>
				<span slot="unChecked">buy</span>
				<span slot="checked">tuy</span>
			</Switch>
			<br />
			<Switch />
		</section>


		<section class="component-card">
			<h1>Button </h1>
			<p>some details </p>
			<Button type="dashed" />
			<Button type="primary" />
			<Button type="link" />
			<Button danger />
			<Button />
		</section>

		<section class="component-card">
			<h1>Dropdown </h1>
			<p>some details </p>
			<Dropdown trigger="hover">
				<Button />
				<div slot="down">
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
				</div>
			</Dropdown>
			<br />
			<Dropdown trigger="click" on:show={({detail})=>{
				console.log(detail) ;
				}}>
				<Button />
				<div slot="down">
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
					<div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
					</div>
				</div>
			</Dropdown>
		</section>


		<section class="component-card">
			<h1>Breadcrumb </h1>
			<p>some details </p>
			<Breadcrumb items={[ '<a href="/sdfdsfds">sdfsdfds</a>' , { href:"/test", title:"test" }, Button, "dsfsd"
				]} />


			<Breadcrumb items={[ '<a href="/home">home</a>' , { href:"/category", title:"category" }, { href:"/list",
				title:"list" }, "product a" ]} />
		</section>


		<section class="component-card">
			<h1>Alert </h1>
			<p>some details </p>
			<Alert title="Text"
				description="Error Description Error Description Error Description Error Description Error Description Error Description" />
			<br />
			<Alert type="success" title="Text"
				description="Error Description Error Description Error Description Error Description Error Description Error Description" />
			<br />
			<Alert type="info" title="Text"
				description="Error Description Error Description Error Description Error Description Error Description Error Description" />
			<br />
			<Alert type="error" title="Text"
				description="Error Description Error Description Error Description Error Description Error Description Error Description" />
		</section>
	</main>
</section>



<style type="text/sass">

	:global(html, body) {
	position: relative;
	width: 100%;
	height: 100%;
	
}
:global(body) {

	color: #333;
	margin: 0;
	padding: 0px;
	box-sizing: border-box;
	font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;

/* Set core body defaults */
min-height: 100vh;
  scroll-behavior: smooth;
  text-rendering: optimizeSpeed;
  line-height: 1.5;

	/* Box sizing rules */
*,
*::before,
*::after {
  box-sizing: border-box;
}

/* Remove default padding */
ul,
ol {
  padding: 0;
  list-style: none;
}

/* Remove default margin */
body,
h1,
h2,
h3,
h4,
p,
ul,
ol,
li,
figure,
figcaption,
blockquote,
dl,
dd {
  margin: 0;
}


/* Remove list styles on ul, ol elements with a class attribute */
ul,
ol {
  list-style: none;
}


/* Make images easier to work with */
img {
  max-width: 100%;
  display: block;
}

/* Natural flow and rhythm in articles by default */
article > * + * {
  margin-top: 1em;
}

/* Inherit fonts for inputs and buttons */
input,
button,
textarea,
select {
  font: inherit;
}

/* Remove all animations and transitions for people that prefer not to see them */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
}



a {
	color: rgb(0,100,200);
	text-decoration: none;
}

a:hover {
	text-decoration: underline;
}

a:visited {
	color: rgb(0,80,160);
}

label {
	display: block;
}

input, button, select, textarea {
	font-family: inherit;
	font-size: inherit;
	padding: 0.4em;
	margin: 0 0 0.5em 0;
	box-sizing: border-box;
	border: 1px solid #ccc;
	border-radius: 2px;
}

input:disabled {
	color: #ccc;
}

input[type="range"] {
	height: 0;
}

button {
	background-color: #f4f4f4;
	outline: none;
}

button:active {
	background-color: #ddd;
}

button:focus {
	border-color: #666;
}


	.content-section{
		display: flex;
		aside{
width: 320px;
		}
		main{
width: 100%;
		}
	}

	.component-card {
    border-bottom: 2px solid #ccc;
    margin-bottom: 32px;
    padding-bottom: 32px;
}

</style>