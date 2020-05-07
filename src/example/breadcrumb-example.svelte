<script>
    import { Breadcrumb, Button } from "../components";
</script>

<section class="component-card">
    <h1>Breadcrumb </h1>
    <p>some details </p>
    <Breadcrumb items={[ '<a href="/sdfdsfds">sdfsdfds</a>' , { href:"/test", title:"test" }, Button, "dsfsd" ]} />
    <Breadcrumb items={[ '<a href="/home">home</a>' , { href:"/category", title:"category" }, { href:"/list",
        title:"list" }, "product a" ]} />
</section>