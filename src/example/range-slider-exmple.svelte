<script>
    import { RangeSlider } from '../components';
    let slider1Options = {
        start: [20, 80],
        connect: true,
        range: {
            'min': 0,
            'max': 100
        }
    }

    let slider2Op = {

        range: {
            'min': 1300,
            'max': 3250
        },

        step: 150,

        // Handles start at ...
        start: [1450, 2050, 2350, 3000],

        // ... must be at least 300 apart
        margin: 300,

        // ... but no more than 600
        limit: 600,

        // Display colored bars between handles
        connect: true,

        // Put '0' at the bottom of the slider
        direction: 'rtl',
        orientation: 'vertical',

        // Move handle on tap, bars are draggable
        behaviour: 'tap-drag',
        tooltips: true,
        // format: wNumb({
        // 	decimals: 0
        // }),

        // Show a scale with the slider
        pips: {
            mode: 'steps',
            stepped: true,
            density: 4
        }
    };


    const oncreated = (event) => {

        debugger;
    }

</script>


<section class="component-card">
    <h1>Range Slider </h1>
    <p>some details </p>
    <RangeSlider options={slider1Options} />
    <br />
    <RangeSlider options={slider2Op} on:created={oncreated} className="vertical" />
</section>
<style type="text/sass">
    :global(.vertical){
    height: 300px;
    margin: auto;
}
</style>