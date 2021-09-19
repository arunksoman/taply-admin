<script>
    import TextInput from "../components/TextInput.svelte";
    import PasswordInput from "../components/PasswordInput.svelte";
    import SubmitBtn from "../components/SubmitBtn.svelte";
    let txt_uname;
    let txt_passwd;
    // $: console.log(txt_uname, txt_passwd);
    let url = 'http://127.0.0.1:5000/'
    async function sendData(data){
        const response = await fetch(url, {
            method: 'POST',
            mode: 'cors',
            cache: 'no-cache',
            credentials: 'same-origin',
            headers: {
                    'Content-Type': 'application/json'
                    // 'Content-Type': 'application/x-www-form-urlencoded',
                },
            body: JSON.stringify(data)
        });
        return response;
    }
    function onSubmit(event){
        console.log(txt_uname, txt_passwd);
        var data = {
            "username": txt_uname,
            "passwd": txt_passwd
        };
        sendData(data).then(response => {
            if (response.status == 200){
                console.log("I got it");
            }
            if (response.status == 404){
                console.log("Response is 404");
            }
            // if (!response.ok) {
            //     throw new Error('Network response was not ok');
            // }
            return response.json();
        }).then(result => {
            console.log(result);
        }).catch(error => {
            console.error('There has been a problem with your fetch operation:', error);
        });
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