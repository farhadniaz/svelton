<script>
    export let title = "";
    export let subTitle = "";
    export let examples;
    export let api = {
        properties: [],
        events: [],
        methods: []
    }
    $: hasEvents = api.events.length;
    $: hasProperties = api.properties.length;
    $: hasMethods = api.methods.length;

</script>

<section class="sectioner">
    <h1>{title}</h1>
    {#if subTitle}
    <p>{subTitle}</p>
    {/if}
    <div class="sectioner__usage">
        Usage:<br/>
        <slot name="usage"/>
    </div>
    <slot name="examples"/>
    <div >
        
      {#if (hasMethods || hasProperties || hasEvents) }  
        API: <br/>
      {/if} 
        {#if hasProperties}
        properties:
        <table class="sectioner__api-table" >
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Description</th>
                    <th>Type</th>
                    <th>Default</th>
                </tr>
            </thead>
            <tbody>
                {#each api.properties as  apiProperty }
                <tr>
                    <td>{apiProperty.name}</td>
                    <td>{apiProperty.description}</td>
                    <td>{apiProperty.type}</td>
                    <td>{apiProperty.default}</td>
                </tr>
                {/each}
            </tbody>
        </table>
        {/if} 
        {#if hasEvents}
        events:
        <table class="sectioner__api-table" >
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Description</th>
                </tr>
            </thead>
            <tbody>
                {#each api.events as  apiEvent }
                <tr>
                    <td>{apiEvent.name}</td>
                    <td>{apiEvent.description}</td>
                </tr>
                {/each}
            </tbody>
        </table>
        {/if}
        {#if hasMethods}
        methods:
        {/if}
    </div>
</section>

<style type="text/sass">

.sectioner {
    border-bottom: 2px solid #ccc;
    margin-bottom: 32px;
    padding-bottom: 32px;
    &__usage{
        margin-top: 32px; 
        margin-bottom: 32px; 
    }
}

.sectioner :global(.example-item ) {
    
    margin-bottom: 32px;

}




.sectioner__api-table {
    direction: ltr;
    empty-cells: show;
    border-collapse: collapse;
    border-spacing: 0;
    margin: 2em 0;
    font-size: 13px;
    line-height: 1.5715;
    border: 1px solid #f0f0f0;
    width: 100%;
}
.sectioner__api-table td:first-child {
    width: 20%;
    color: #595959;
    font-weight: 600;
}

.sectioner__api-table  th, .sectioner__api-table  td {
    padding: 12px;
    border-color: #f0f0f0;
    border-width: 1px 0;
}
.sectioner__api-table  th, .sectioner__api-table  td {
    padding: 16px 24px;
    text-align: left;
    border: 1px solid #f0f0f0;
}

.sectioner__api-table th {
    font-weight: normal;
    background: #f8f8f8;
}

</style>