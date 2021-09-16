<script>
    import TextInput from "../components/TextInput.svelte";
    import SubmitBtn from "../components/SubmitBtn.svelte";
</script>

<div class="min-h-screen bg-gray-100 py-6 grid place-items-center sm:py-12">
    <div class="bg-white shadow-lg min-w-max md:w-96 px-8 py-8 rounded-md">
        <div class="flex justify-center mb-4">
            <img class="w-32 h-32 rounded-full" src="/avatar-male.png" alt="">
        </div>
        <TextInput type="text" placeholder="Username" name="txt_uname" />
        <TextInput type="password" placeholder="Password" name="txt_passwd" />
        <SubmitBtn value="login"/>
    </div>
</div>