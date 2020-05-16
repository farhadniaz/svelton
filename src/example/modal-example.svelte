<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Modal, Button } from "../components";
    let modalVisible = false;

    let usage = `
    import { Modal, Button } from 'svelton';
    let modalVisible = false;
    <Modal bind:visible={modalVisible} 
    title="modal title" 
    on:ok={()=>{alert("ok")}}
    on:cancel={()=>{alert("cancel")}}>
                Some contents...<br />
                Some contents...<br />
                Some contents...
    </Modal>

    <Button on:click={()=>modalVisible=!modalVisible}>modalVisible</Button>

    `;





    let api = {
        properties: [
            {
                name: "backdropClosable",
                description: "An array of Breadcrumb items",
                type: "[{title,href, onClick} | html]",
                default: ""
            },
            {
                name: "visible",
                description: "seprator of items",
                type: "string | svelte component",
                default: "/"
            },
            {
                name: "title",
                description: "seprator of items",
                type: "string | svelte component",
                default: "/"
            }
        ],
        events: [
            {
                name: "cancel",
                description: "will be trigger whenever clicking on the modal cancel button "
            },
            {
                name: "close",
                description: "will be trigger whenever the modal close"
            },
            {
                name: "ok",
                description: "will be trigger whenever clicking on the modal ok button"
            }

        ],
        methods: [],
        slot: [

        ]
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
            <Modal bind:visible={modalVisible} title="modal title" on:ok={()=>{alert("ok")}}
                on:cancel={()=>{alert("cancel")}}>
                Some contents...<br />
                Some contents...<br />
                Some contents...
            </Modal>
            <Button on:click={()=>modalVisible=!modalVisible}>modalVisible</Button>
        </div>
    </div>
</Sectioner>