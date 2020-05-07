<script>
    import page from 'page';
    import Home from './layout/home.svelte';


    import {
        AlertExample,
        BreadcrumbExample,
        CheckboxExample,
        DrawerExample,
        DropdownExample,
        FileuploadExample,
        InputExample,
        ModalExample,
        PaginationExample,
        RadioExample,
        RangeSliderExample,
        RateExample,
        SwitchExample,
        TagExample,
        TreeExample,
        ButtonExample
    } from './example';



    // set default component
    let current = Home;

    // Map routes to page. If a route is hit the current
    // reference is set to the route's component
    page('/', () => (current = Home));
    page('/alert', () => (current = AlertExample));
    page('/breadcrumb', () => (current = BreadcrumbExample));
    page('/drawer', () => (current = DrawerExample));
    page('/checkbox', () => (current = CheckboxExample));
    page('/dropdown', () => (current = DropdownExample));
    page('/fileupload', () => (current = FileuploadExample));
    page('/input', () => (current = InputExample));
    page('/modal', () => (current = ModalExample));
    page('/pagination', () => (current = PaginationExample));
    page('/radio', () => (current = RadioExample));
    page('/range-slider', () => (current = RangeSliderExample));
    page('/Rate', () => (current = RateExample));
    page('/switch', () => (current = SwitchExample));
    page('/tag', () => (current = TagExample));
    page('/tree', () => (current = TreeExample));
    page('/button', () => (current = ButtonExample));

    // activate router
    page.start();
</script>

<svelte:component this={current} />