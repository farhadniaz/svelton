<script>
    import { Pagination } from '../components';
</script>
<section class="component-card">
    <h1>Pagination </h1>
    <p>some details </p>

    <Pagination />
    <br />
    <Pagination total={1000} currentPage={10} perPage={10} range={10} />

</section>