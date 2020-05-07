<script>
    import { Checkbox } from '../components';
    let group = null;
	// const groupChanges = ({ detail }) => group = detail;
	let singleCheckBox = "";
	let groupCheckBox = [];
</script>

<section class="component-card">
    <h1>Checkbox </h1>
    <p>some details </p>
    <Checkbox>value singleCheckBox
        <input type="checkbox" bind:group={singleCheckBox} value="single" slot="input">
    </Checkbox>
    {singleCheckBox}
    <Checkbox>group Checkbox
        <input type="checkbox" bind:group={groupCheckBox} value="Rice" slot="input">
    </Checkbox>
    <Checkbox>group Checkbox
        <input type="checkbox" bind:group={groupCheckBox} value="gop" slot="input">
    </Checkbox>
    {groupCheckBox}
</section>