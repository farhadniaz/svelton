<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Alert } from "../components";

    let usage = `
    import { Alert } from 'svelton';
    <Alert type="success" title="Access"
        description="Your access was granted!" />
    `;

    let api = {
        properties: [
            {
                name: "title",
                description: "Title of alert ",
                type: "string",
                default: ""
            },
            {
                name: "description",
                description: "description of alert",
                type: "string",
                default: ""
            },
            {
                name: "closeable",
                description: "Indecate that alert can be close",
                type: "boolean",
                default: "true"
            },
            {
                name: "type",
                description: "The alert type || success, info, warning, error",
                type: "string",
                default: "warning"
            },
        ],
        events: [{
            name: "close",
            description: "will be trigger whenever alert closed "
        }],
        methods: []
    }

</script>

<Sectioner title="Alert" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>

    <div slot="examples">
        <div class="example-item">
            <Alert title="Warning title" description="Warning Description Warning Description Warning 
                Description Warning Description Warning Description Warning 
                Description" />
        </div>
        <div class="example-item">
            <Alert type="success" title="Success title"
                description="success Description success Description success Description success Description success Description success Description" />
            <Highlighter>
                {`
                import { Alert } from 'svelton';
                <Alert type="success" title="Success title" description="success Description success .." />
                `}
            </Highlighter>

        </div>
        <div class="example-item">
            <Alert type="info" title="Info title" description="Info  Description
                 Error Description Info  Description Info 
                  Description Info  Description Info 
                   Description" />
            <Highlighter>
                {`
                import { Alert } from 'svelton';
                <Alert type="info" title="Info title" description="Info Description Info .." />
                `}
            </Highlighter>
        </div>
        <div class="example-item">
            <Alert type="error" title="Error title"
                description="Error Description Error Description Error Description Error Description Error Description Error Description" />

            <Highlighter>
                {`
                import { Alert } from 'svelton';
                <Alert type="error" title="Error title" description="Error Description Error .." />
                `}
            </Highlighter>

        </div>
    </div>
</Sectioner>