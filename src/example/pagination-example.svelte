<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Pagination } from '../components';


    let usage = `
    import { Pagination } from 'svelton';
    <Pagination />
    `;

    let usage2 = `
    import { Pagination } from 'svelton';
    <Pagination 
    on:change={(event)=>{
        const {detail}=event;
        console.log("page number is " + detail);
    }}
    total={1000} 
    currentPage={10} 
    perPage={10} 
    range={10} 
    />
    `;

    let usage3 = `
    import { Pagination } from 'svelton';

    <Pagination 
        total={1000} 
        currentPage={1} 
        perPage={10} 
        range={3} />
    `;

    let api = {
        properties: [
            {
                name: "total",
                description: "Total items count",
                type: "number",
                default: "100"
            },
            {
                name: "currentPage",
                description: "Current page number",
                type: "number",
                default: "1"
            },
            {
                name: "perPage",
                description: "Number of data items per page	",
                type: "number",
                default: "5"
            },
            {
                name: "range",
                description: "Page items in view",
                type: "number",
                default: "5"
            },
        ],
        events: [
            {
                name: "change",
                description: "Called when the page number is changed"
            },
        ],
        methods: [],
        slot: [

        ]
    }

</script>


<Sectioner title="Pagination" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Pagination />
        </div>
        <div class="example-item">
            <Highlighter>
                {usage2}
            </Highlighter>
            <Pagination on:change={(event)=>{
                const {detail}=event;
                alert("page number changed to " + detail);
                }}
                total={1000} currentPage={10} perPage={10} range={10} />
        </div>
        <div class="example-item">
            <Highlighter>
                {usage3}
            </Highlighter>
            <Pagination total={1000} currentPage={1} perPage={10} range={3} />
        </div>
    </div>
</Sectioner>