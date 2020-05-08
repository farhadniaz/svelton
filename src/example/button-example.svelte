<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Button } from "../components";

    let usage = `
    import { Button } from 'svelton';
    <Button />
    `;

    let allUsage = `
    import { Button } from 'svelton';
    <Button type="dashed" />
    <Button type="primary" />
    <Button type="link" />
    <Button danger />
    `;
    let allUsage2 = `
    import { Button } from 'svelton';
    const onClick=()=> alert('clicked');
    <Button type="dashed" on:click={onClick}>click me</Button>
    <Button type="primary" on:click={onClick}>click me</Button>
    <Button type="link" on:click={onClick}>click me</Button>
    <Button danger on:click={onClick}>click me</Button>
    `;
    const onClick = () => alert('clicked');
    let api = {
        properties: [
            {
                name: "type",
                description: "type of button, values can be, dashed | primary | link | default",
                type: "string",
                default: "default"
            },
            {
                name: "danger",
                description: "set the danger status of button",
                type: "boolean",
                default: "false"
            }
        ],
        events: [],
        methods: []
    }
</script>


<Sectioner title="Button" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Button />
        </div>
        <div class="example-item">
            All types :<br />
            <Button type="dashed" />
            <Button type="primary" />
            <Button type="link" />
            <Button danger />
            <Highlighter>
                {allUsage}
            </Highlighter>
        </div>


        <div class="example-item">
            <Button type="dashed" on:click={onClick}>click me</Button>
            <Button type="primary" on:click={onClick}>click me</Button>
            <Button type="link" on:click={onClick}>click me</Button>
            <Button danger on:click={onClick}>click me</Button>
            <Highlighter>
                {allUsage2}
            </Highlighter>
        </div>



    </div>




</Sectioner>