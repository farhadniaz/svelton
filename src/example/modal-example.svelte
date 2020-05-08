<script>
    import { Modal, Button } from "../components";
    let modalVisible = false;
  

</script>
<section class="component-card">
    <h1>Modal</h1>
    <p>some details </p>
    <Modal bind:visible={modalVisible} 
    title="my title" 
    on:ok={()=>{alert("ok")}}
    on:cancel={()=>{alert("cancel")}}>
    body     <br/>
    dsfds
    <br/>

    lastOutSideFocusNodesdf     <br/>
    solid     <br/>
    <br/>
    lastOutSideFocusNodesfd
    <s>
        <br/>
    </s>
</Modal>
        <Button on:click={()=>modalVisible=!modalVisible}>modalVisible</Button>
</section>