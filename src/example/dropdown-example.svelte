<script>
    import Highlighter from '../example/sectioner/highlighter.svelte'
    import Sectioner from './sectioner/index.svelte';
    import { Dropdown, Button } from '../components';

    let usage = `
    import { Dropdown, Button } from 'svelton';

    <Dropdown trigger="hover">
            <Button type="link">hover me</Button>
            <div slot="down">
                <div class="item">1st item</div>
                <div class="item">2nd item</div>
                <div class="item">3rd item</div>
            </div>
    </Dropdown>
    `;
    let usage2 = `
    import { Dropdown, Button } from 'svelton';

    <Dropdown trigger="hover">
        <Button danger>hover me</Button>
        <div slot="down">
            <div class="item">1st item</div>
            <div class="item">2nd item</div>
            <div class="item">3rd item</div>
        </div>
    </Dropdown>
       
    

    <Dropdown trigger="hover">
                <Button type="dashed">hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
    </Dropdown>

    

    <Dropdown trigger="hover">
                <Button type="primary">hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
    </Dropdown>
            `


    let usage3 = `
    import { Dropdown, Button } from 'svelton';


    <Dropdown trigger="click" on:show={({detail})=>{
                console.log(detail? 'opend':'closed') ;
                }}>
                <Button>click me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>

    `;

    let api = {
        properties: [
            {
                name: "trigger",
                description: "click | hover",
                type: "string",
                default: "click"
            },
        ],
        events: [

            {
                name: "show",
                description: "will be trigger whenever dropdown shows the down  "
            },
        ],
        methods: [],
        slot: [

        ]
    }

</script>




<Sectioner title="Dropdown" api={api}>
    <span slot="usage">
        <Highlighter>
            {usage}
        </Highlighter>
    </span>
    <div slot="examples">
        <div class="example-item">
            <Dropdown trigger="hover">
                <Button type="link">hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>
        </div>

        <div class="example-item">
            <Highlighter>
                {usage2}
            </Highlighter>
            <Dropdown trigger="hover">
                <Button danger>hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>
            <br /> <br />
            <Dropdown trigger="hover">
                <Button type="dashed">hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>
            <br /><br />
            <Dropdown trigger="hover">
                <Button type="primary">hover me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>
        </div>
        <div class="example-item">
            <Highlighter>
                {usage3}
            </Highlighter>
            <Dropdown trigger="click" on:show={({detail})=>{
                console.log(detail) ;
                }}>
                <Button>click me</Button>
                <div slot="down">
                    <div class="item">1st item</div>
                    <div class="item">2nd item</div>
                    <div class="item">3rd item</div>
                </div>
            </Dropdown>
        </div>

    </div>
</Sectioner>