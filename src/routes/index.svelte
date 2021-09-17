<script>
    import TextInput from "../components/TextInput.svelte";
    import PasswordInput from "../components/PasswordInput.svelte";
    import SubmitBtn from "../components/SubmitBtn.svelte";
    let txt_uname;
    let txt_passwd;
    // $: console.log(txt_uname, txt_passwd);
    function onSubmit(event){
        console.log(txt_uname, txt_passwd);
    }
</script>

<div class="min-h-screen bg-gray-100 py-6 grid place-items-center sm:py-12">
    <div class="bg-white shadow-lg min-w-max md:w-96 px-8 py-8 rounded-md">
        <div class="flex justify-center mb-4">
            <img class="w-32 h-32 rounded-full" src="/avatar-male.png" alt="">
        </div>
        <form on:submit|preventDefault={onSubmit}>
            <TextInput placeholder="Username" name="txt_uname" bind:value={txt_uname} />
            <PasswordInput placeholder="Password" name="txt_passwd" bind:value={txt_passwd} />
            <SubmitBtn value="login"/>
        </form>
    </div>
</div>