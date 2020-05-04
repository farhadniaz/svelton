<script>
    import { onMount } from 'svelte';
    import 'filepond/dist/filepond.css';
    import * as FilePond from 'filepond';
    let uploadContainer;

    onMount(() => {
        // Create a multi file upload component
        const pond = FilePond.create({
            multiple: true,
            name: 'filepond'
        });
        // Add it to the DOM
        uploadContainer.appendChild(pond.element);
    })

</script>


<div bind:this={uploadContainer}>

</div>