<script>
    // import Highlight from 'svelte-highlight';
    // import 'svelte-highlight/styles/github.css';
    import hljs from 'highlight.js';
    import 'highlight.js/styles/github.css';
    import hljsDefineSvelte from './lng.js'
    hljs.registerLanguage("svelte", hljsDefineSvelte);
    import { onMount } from 'svelte';
    let codeSection;
    onMount(() => {
        hljs.highlightBlock(codeSection);
    });
</script>
<pre bind:this={codeSection}>
        <code class="html">
        <slot/>
    </code>
</pre>