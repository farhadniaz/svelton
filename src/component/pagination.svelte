<script>
    import LeftSvg from '../icons-svg/outlined/left.svg';
    import RightSvg from '../icons-svg/outlined/right.svg';
    import DoubleRightSvg from '../icons-svg/outlined/double-right.svg';
    import DoubleLeftSvg from '../icons-svg/outlined/double-left.svg';

    export let total = 100;
    export let currentPage = 1;
    export let perPage = 5;
    export let range = 5;
    let pages = total / perPage;

    let rangeSides = Math.floor(range / 2);
    let left, right, hasStartSteper, hasEndSteper, calculateRangeItems;

    $: left = currentPage - rangeSides;
    $: left = left < 1 ? 1 : left;
    $: left = left > (pages - (range - 1)) ? (pages - (range - 1)) : left;

    $: right = (currentPage + rangeSides);
    $: right = right < 5 ? 5 : right;
    $: right = right > pages ? pages : right;

    const getItems = (left, right) => {
        let ii = [];
        for (let i = left; i <= right; i++) {
            ii.push(i);
        }
        return ii;
    }
    $: calculateRangeItems = getItems(left, right);

    $: hasStartSteper = left > 1;
    $: hasEndSteper = right < pages;
    const setPage = (page) => {
        if (page > 0 && page < pages + 1) {
            currentPage = page;
        }
    }

</script>
<ul class="svelton-pagination">
    <li class="svelton-pagination__item" on:click={()=>setPage(currentPage-1) }>{@html LeftSvg}</li>

    {#if hasStartSteper}
        <li  class="svelton-pagination__item" on:click={()=>setPage(1) }>1</li>
        <li  class="svelton-pagination__item" on:click={()=>setPage(currentPage-5) }>
            <i  class="dots">•••</i>
            <i class="double">{@html DoubleLeftSvg}</i>
        </li> 
    {/if}

    {#each calculateRangeItems as item,pageIndex }
        <li 
        class={`svelton-pagination__item ${item==currentPage?'current-page':''}`}
         on:click={()=>setPage(item) }>{item}</li>
    {/each}
  
    {#if hasEndSteper}
        <li  class="svelton-pagination__item" on:click={()=>setPage(currentPage+5) }>
            <i  class="dots">•••</i>
            <i class="double">{@html DoubleRightSvg}</i>
        </li> 
        <li  class="svelton-pagination__item" on:click={()=>setPage(pages) }>{pages}</li>
    {/if}

    <li  class="svelton-pagination__item" on:click={()=>setPage(currentPage+1) }>{@html RightSvg}</li>
    
</ul>

<style type="text/sass">


.svelton-pagination{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    color: rgba(0,0,0,.65);
    font-size: 14px;
    font-variant: tabular-nums;
    line-height: 1.5715;
    list-style: none;
    font-feature-settings: 'tnum';
}
.svelton-pagination__item{
    display: inline-block;
    min-width: 32px;
    height: 32px;
    margin-right: 8px;
    font-family: Arial;
    line-height: 30px;
    text-align: center;
    vertical-align: middle;
    list-style: none;
    background-color: #fff;
    border: 1px solid #d9d9d9;
    border-radius: 2px;
    outline: 0;
    cursor: pointer;
    user-select: none;
    .double{
        display: none;
    }
    &:hover
    {
        .double{
            display: block;
        }  
        .dots{
            display: none; 
        }
    }
  
}
    
.svelton-pagination :global(.svelton-pagination__item.current-page){
    font-weight: 500;
    background: #fff;
    border-color: #1890ff;
  }
  
</style>