<script>
    import page from 'page';
    import { routes } from '../example';
    import { Button } from "../components";

    const navigate = (path) => { page(path); }
</script>


<aside>
    <ul>
        {#each routes as routeItem}
            <li>
                <Button type="link" on:click={()=>navigate(routeItem.href)}>
                    {routeItem.title}
                </Button>
               </li>
        {/each}
    </ul>
</aside>