<script>
  export let controlType;
  export let id;
  export let label;
  export let rows;
  export let type;
  export let value;
  export let placeholder;
</script>

<style>
  .inputform {
    border-color: #d8d8d8;
    border-style: solid;
    outline: none;
    border-width: 1px;
    border-radius: 4px;
    line-height: 16px;
    padding: 10px;
    width: 98%;
    font-size: 0.9rem;
  }
  .inputform:focus {
    border-color: var(--main_black);
  }

  label {
    margin-bottom: 1rem;
    width: 100%;
    font-family: var(--main_header);
  }
  textarea {
    font-family: inherit;
  }

  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }
</style>

<div class="form-control">
  <label for={id}>{label}</label>
  {#if controlType === 'textarea'}
    <textarea class="inputform" {type} {id} {placeholder} {value} on:input />
  {:else if controlType === 'date'}
    <input type="date" {id} {value} on:input />
  {:else if controlType === 'number'}
    $<input type="number" {id} {value} on:input />
  {:else}
    <input class="inputform" type="text" {id} {placeholder} {value} on:input />
  {/if}
</div>
