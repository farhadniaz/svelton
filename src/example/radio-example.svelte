<script>
    import { Radio } from '../components';
    let radiodata = "";
    let radiodataGroup = [];
</script>

<section class="component-card">
    <h1>Radio </h1>
    <p>some details </p>
    {radiodata}

    <Radio>
        sdfsdfdsf
        <input type="radio" bind:group={radiodata} value="single" slot="input" />

    </Radio>
    <br />
    <Radio>
        a
        <input type="radio" bind:group={radiodataGroup} value="a" slot="input" />

    </Radio>
    <Radio>
        <input type="radio" bind:group={radiodataGroup} value="b" slot="input" />
    </Radio>
    {radiodataGroup}
</section>