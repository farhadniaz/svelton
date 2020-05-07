<script>
	import Highlighter from '../../example/sectioner/highlighter.svelte'
	import Sectioner from '../sectioner/index.svelte';

	import { Tree } from '../../components';
	import FileSVG from './file-svg.svelte';
	import FolderSVG from './folder-svg.svelte';
	let root = [
		{
			type: 'root',
			name: 'Important work stuff',
			items: [
				{ type: 'file', name: 'quarterly-results.xlsx' }
			]
		},
		{
			type: 'root',
			name: 'Animal GIFs',
			items: [
				{
					type: 'root',
					name: 'Dogs',
					items: [
						{ type: 'file', name: 'treadmill.gif' },
						{ type: 'file', name: 'rope-jumping.gif' }
					]
				},
				{
					type: 'root',
					name: 'Goats',
					items: [
						{ type: 'file', name: 'parkour.gif' },
						{ type: 'file', name: 'rampage.gif' }
					]
				},
				{ type: 'file', name: 'cat-roomba.gif' },
				{ type: 'file', name: 'duck-shuffle.gif' },
				{ type: 'file', name: 'monkey-on-a-pig.gif' }
			]
		},
		{ type: 'file', name: 'TODO.md' }
	];

	let usage = `
	import { Tree } from 'svelton';
	import FileSVG from './file-svg.svelte';
	import FolderSVG from './folder-svg.svelte';
	let root = [
		{
			type: 'root',
			name: 'Important work stuff',
			items: [
				{ type: 'file', name: 'quarterly-results.xlsx' }
			]
		},
		{
			type: 'root',
			name: 'Animal GIFs',
			items: [
				{
					type: 'root',
					name: 'Dogs',
					items: [
						{ type: 'file', name: 'treadmill.gif' },
						{ type: 'file', name: 'rope-jumping.gif' }
					]
				},
				{
					type: 'root',
					name: 'Goats',
					items: [
						{ type: 'file', name: 'parkour.gif' },
						{ type: 'file', name: 'rampage.gif' }
					]
				},
				{ type: 'file', name: 'cat-roomba.gif' },
				{ type: 'file', name: 'duck-shuffle.gif' },
				{ type: 'file', name: 'monkey-on-a-pig.gif' }
			]
		},
		{ type: 'file', name: 'TODO.md' }
	];

	<Tree name="Home" items={root} expanded icon={FolderSVG} leafIcon={FileSVG} />
	`;
</script>


<Sectioner title="Tree">
	<span slot="usage">
		<Highlighter>
			{usage}
		</Highlighter>
	</span>
	<div slot="examples">
		<div class="example-item">
			<Tree name="Home" items={root} expanded icon={FolderSVG} leafIcon={FileSVG} />
		</div>
	</div>
</Sectioner>