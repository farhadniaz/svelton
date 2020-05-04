<script>
	import { Tree } from '../components';
	import FolderSVG from '../components/icons-svg/outlined/folder.svg';
	import FileSVG from '../components/icons-svg/outlined/file.svg';
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
</script>

<Tree name="Home" items={root} expanded icon={FolderSVG} leafIcon={FileSVG} />