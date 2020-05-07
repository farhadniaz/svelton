<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Rate } from '../components';
    let usage = `
    import { Rate } from 'svelton';
    <Rate  />
    `;

    let usage2 = `
    import { Rate } from 'svelton';
    <Rate value={3} count={6} />
    `;

    let usage3 = `
    import { Rate } from 'svelton';
    const onChange = (event) => {
        alert(event.detail);    
    }
    <Rate  count={4} on:change={onChange}/>
    `;



    let api = {
        properties: [
            {
                name: "count",
                description: "indicate value of switch",
                type: "Boolean",
                default: "false"
            },
            {
                name: "color",
                description: "indicate value of switch",
                type: "Boolean",
                default: "false"
            },
            // {
            //     name: "color",
            //     description: "indicate value of switch",
            //     type: "Boolean",
            //     default: "false"
            // }
        ],
        events: [{
            name: "change",
            description: "will be trigger whenever value changes "
        }],
        methods: []
    };

    const onChange = (event) => {
        alert(event.detail);
    }
</script>

<Sectioner title="Rate" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Rate />
        </div>

        <div class="example-item">
            <Rate value={3} count={6} />
            <Highlighter>
                {usage2}
            </Highlighter>
        </div>
        <div class="example-item">
            <Rate count={4} on:change={onChange} />
            <Highlighter>
                {usage3}
            </Highlighter>
        </div>

    </div>
</Sectioner>