<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Radio } from '../components';
    let radiodata = "";
    let radiodataGroup = [];
    let usage = `
    import { Radio } from 'svelton';
    let data = "";
    <Radio>
        <input slot="input" type="radio" bind:group={data} value="single" />
        single
    </Radio>
    `;

    let groupUsage = ` 
    import { Radio } from 'svelton';
    let radiodataGroup = [];
                <Radio>
                    a
                    <input type="radio" bind:group={radiodataGroup} value="a" slot="input" />
                </Radio>
                <Radio>
                    b
                    <input type="radio" bind:group={radiodataGroup} value="b" slot="input" />
                </Radio>`;


</script>

<Sectioner title="Radio">
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            Status: {radiodata}<br />
            <Radio>
                <input slot="input" type="radio" bind:group={radiodata} value="single" />
                single
            </Radio>
        </div>
        <div class="example-item">
            Group: {radiodataGroup}<br />
            <Radio>
                a <input type="radio" bind:group={radiodataGroup} value="a" slot="input" />
            </Radio>
            <Radio>
                b <input type="radio" bind:group={radiodataGroup} value="b" slot="input" />
            </Radio>
            <Highlighter>
                {groupUsage}
            </Highlighter>
        </div>

    </div>
</Sectioner>