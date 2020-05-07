<script>
    import { Tag } from '../components';
</script>

<section class="component-card">
    <h1>Tag </h1>
    <p>some details </p>
    <Tag>one</Tag>
    <Tag closable>farhad</Tag>
    <Tag color="magenta" closable>magenta</Tag>
    <Tag color="red" closable on:close={({detail})=>{alert(detail)}}>red</Tag>
    <Tag color="volcano" closable>volcano</Tag>
    <Tag color="orange" closable>orange</Tag>
    <Tag color="gold" closable>gold</Tag>
    <Tag color="black" closable>black</Tag>
    <Tag color="lime" closable>lime</Tag>
    <Tag color="green" closable>green</Tag>
    <Tag color="cyan" closable>cyan</Tag>
    <Tag color="blue" closable>blue</Tag>
    <Tag color="geekblue" closable>geekblue</Tag>
    <Tag color="purple" closable className="sdfsdfds">purple</Tag>
</section>