<script>
    import { onMount, createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    import noUiSlider from 'nouislider';
    import 'nouislider/distribute/nouislider.css';

    export let options = {}
    export let className = ""
    
    let slider;
    let noUiSliderInstance;
    onMount(() => {
        noUiSliderInstance = noUiSlider.create(slider, options);

        dispatch('created', noUiSliderInstance);

    });

</script>

<div class={`${className}`} bind:this={slider}></div>