<script>

    import { Switch } from '../components';
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';

    let usage = `
    import { Switch } from 'svelton';
    <Switch/>
    `;
    let api = {
        properties: [
            {
                name: "switched",
                description: "indicate value of switch",
                type: "Boolean",
                default: "false"
            }
        ],
        events: [{
            name: "change",
            description: "will be triger whenever value changes "
        }],
        methods: []
    }
</script>

<Sectioner title="Switch" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>

    <span slot="examples">
        <div class="example-item">
            Enable:
            <Switch />
        </div>
        <div class="example-item">
            State: <Switch>
                <span slot="unChecked">Off</span>
                <span slot="checked">On</span>
            </Switch>
            <br />
            <Highlighter>
                {`
                <Switch>
                    <span slot="unChecked">Off</span>
                    <span slot="checked">On</span>
                </Switch>`}
            </Highlighter>

        </div>

        <div class="example-item">
            Color: <Switch>
                <span slot="unChecked">Red</span>
                <span slot="checked">Blue</span>
            </Switch>
            <br />
            <Highlighter>
                {`
                <Switch>
                    <span slot="unChecked">Red</span>
                    <span slot="checked">Blue</span>
                </Switch>`}
            </Highlighter>
        </div>

    </span>



</Sectioner>