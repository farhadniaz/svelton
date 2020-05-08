<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Tag } from '../components';

    let usage = `
    import { Tag } from 'svelton';
    <Tag>one</Tag>
    `;

    let usageAll = `
    import { Tag } from 'svelton';
    <Tag closable>default</Tag>
    <Tag color="magenta" closable>magenta</Tag>
    <Tag color="red" closable on:close={(event)=>{alert('closed')}}>red</Tag>
    <Tag color="volcano" closable>volcano</Tag>
    <Tag color="orange" closable>orange</Tag>
    <Tag color="gold" closable>gold</Tag>
    <Tag closable style="color:white;background-color: black;">black</Tag>
    <Tag color="lime" closable>lime</Tag>
    <Tag color="green" closable>green</Tag>
    <Tag color="cyan" closable>cyan</Tag>
    <Tag color="blue" closable>blue</Tag>
    <Tag color="geekblue" closable>geekblue</Tag>
    <Tag color="purple" closable className="my-class" >purple</Tag>
    `;


    let api = {
        properties: [
            {
                name: "color",
                description: "the color of tag",
                type: "string values acn be , red | volcano | orange | gold | black | lime | green | cyan | blue | geekblue | purple | magenta",
                default: ""
            },
            {
                name: "closable",
                description: "abaling the tag to be close buy clicking",
                type: "boolean",
                default: "true"
            },
            {
                name: "className",
                description: "custom css class for tag",
                type: "string",
                default: ""
            },

        ],
        events: [{
            name: "close",
            description: "will be trigger whenever the tag closed "
        }],
        methods: []
    }
</script>


<Sectioner title="Tag" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Tag>one</Tag>
        </div>
        <div class="example-item">
            <Highlighter>
                {usageAll}
            </Highlighter>
            <Tag closable>default</Tag>
            <Tag color="magenta" closable>magenta</Tag>
            <Tag color="red" closable on:close={(event)=>{alert('closed')}}>red</Tag>
            <Tag color="volcano" closable>volcano</Tag>
            <Tag color="orange" closable>orange</Tag>
            <Tag color="gold" closable>gold</Tag>
            <Tag closable style="color:white;background-color: black;">black</Tag>
            <Tag color="lime" closable>lime</Tag>
            <Tag color="green" closable>green</Tag>
            <Tag color="cyan" closable>cyan</Tag>
            <Tag color="blue" closable>blue</Tag>
            <Tag color="geekblue" closable>geekblue</Tag>
            <Tag color="purple" closable className="my-class" >purple</Tag>
        </div>
    </div>
</Sectioner>