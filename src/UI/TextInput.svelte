       <script>
       export let controleType;
       export let id;
       export let label;
       export let rows;
       export let value;
       </script>


         <div class="form-control">
            <label for="{id}">{label}}n</label>
       {#if controleType === 'textarea'}
            <textarea rows="{rows}}" id="{id}" value={value} on:input/>
       {:else}
            <input type="text" id="{id}" bvalue={value} on:input>
         {/if}
        </div>