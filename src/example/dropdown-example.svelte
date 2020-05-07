<script>
    import { Dropdown, Button } from '../components';
</script>

<section class="component-card">
    <h1>Dropdown </h1>
    <p>some details </p>
    <Dropdown trigger="hover">
        <Button />
        <div slot="down">
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
        </div>
    </Dropdown>
    <br />
    <Dropdown trigger="click" on:show={({detail})=>{
        console.log(detail) ;
        }}>
        <Button />
        <div slot="down">
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
            <div>dfdsfdsfsdfsdfsdfsdf dsfdsfds dsfsdf
            </div>
        </div>
    </Dropdown>
</section>