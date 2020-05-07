<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Checkbox } from '../components';
    let group = null;
    // const groupChanges = ({ detail }) => group = detail;
    let isOk = "";
    let groupCheckBox = []; 
    let usage = `
    import { Checkbox } from 'svelton';
    let data = "";
    <Checkbox>value singleCheckBox
        <input type="checkbox" bind:group={data} value="isOk" slot="input">
    </Checkbox>
    `;

    let groupUsage = `
    import { Checkbox } from 'svelton';
    let groupCheckBox = []; 
    <Checkbox> Rice
        <input type="checkbox" bind:group={groupCheckBox} value="Rice" slot="input">
    </Checkbox>
    <Checkbox> Egg
        <input type="checkbox" bind:group={groupCheckBox} value="Egg" slot="input">
    </Checkbox>`;


</script>

<Sectioner title="Checkbox">
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            Single checkbox:<br />
            <Checkbox>isOk
                <input type="checkbox" bind:group={isOk} value="yes" slot="input">
            </Checkbox>
            {isOk}
        </div>
        <div class="example-item">
            Grouped checkbox:<br />
            order: {groupCheckBox}<br />
            <Checkbox>Rice
                <input type="checkbox" bind:group={groupCheckBox} value="Rice" slot="input">
            </Checkbox>
            <Checkbox>Egg
                <input type="checkbox" bind:group={groupCheckBox} value="Egg" slot="input">
            </Checkbox>
            <Highlighter>
                {groupUsage}
            </Highlighter>
        </div>
    </div>
</Sectioner>