<script>
	import page from 'page';
	const navigate = (path) => { page(path); }
</script>

<header>
	<h1 on:click={()=>navigate("/")}>svelton</h1>
</header>

<style type="text/sass">
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
		margin: 0;
	}

	.content-section{
		display: flex;
		aside{
width: 320px;;
		}
		main{
width: 100%;
		}
	}
</style>