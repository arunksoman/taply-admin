<script>
    export let placeholder;
    export let name = "";
    export let value = "";
    let id=name;
    let label = name;
</script>

<label for={label}></label>
<input class="border border-2 border-blue-500 mt-5 mb-3 bg-white appearance-none block w-full rounded-md py-2 px-2 focus:outline-none" type="password" bind:value name={name} {id} placeholder={placeholder}>