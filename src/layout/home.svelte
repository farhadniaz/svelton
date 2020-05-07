<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    let u = `import {Button} from 'svelton';
<Button type="primary">My Button</Button>`;
</script>
<div>
    <h1>Svelton UI Library</h1>
    <p>Svelton is a set of high-quality Svelte components with Powerful customization.</p>
    <br/>
    <p>RTL support</p>
    <br />
    <h2>Install:</h2>
    <Highlighter>
        npm install svelton
    </Highlighter>
    or
    <Highlighter>
        yarn add svelton
    </Highlighter>

    <br />
    <h2>Usage:</h2>
    <Highlighter>
        {u}
    </Highlighter>


</div>