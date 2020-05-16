<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Breadcrumb, Button } from "../components";

    const onClick = () => alert('clicked');
    const items = [
        '<a href="/">home</a>',
        {
            href: "/products", title: "products", onClick: (event) => {
                event.preventDefault();
                event.stopPropagation();
                alert('products item clicked')
            }
        },
        "product name"]


    const items2 = [
        {
            href: "/", title: "home"
        },
        {
            href: "/alert", title: "alert component"
        },
        "alert"]

    let usage = `
    import { Breadcrumb } from 'svelton';
    const items=[ 
        '<a href="/">home</a>' , 
        { href:"/products", title:"products" , onClick: (event) => {
                event.preventDefault();
                event.stopPropagation();
                alert('products item clicked')
            }
        },
        "product name"
        ]
    <Breadcrumb items={} />
    `;


    let usage2 = `
    import { Breadcrumb } from 'svelton';
    const items=[
        {
            href: "/", title: "home"
        },
        {
            href: "/alert", title: "alert component"
        },
        "alert"];
    <Breadcrumb items={} />
    `;
    let api = {
        properties: [
            {
                name: "items",
                description: "An array of Breadcrumb items",
                type: "[{title,href, onClick} | html]",
                default: ""
            },
            {
                name: "seprator",
                description: "seprator of items",
                type: "string | svelte component",
                default: "/"
            }
        ],
        events: [],
        methods: []
    }

</script>

<Sectioner title="Breadcrumb" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Breadcrumb items={items} />
        </div>
        <div class="example-item">
            <Highlighter>
                {usage2}
            </Highlighter>
            <Breadcrumb items={items2} />
        </div>
    </div>
</Sectioner>