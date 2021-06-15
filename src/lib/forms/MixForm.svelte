<script>
    const klaviyo_API = 'https://a.klaviyo.com/api/v2/list/Yra3hD/subscribe?api_key=pk_5ae8611bb3e4a7ce8fed257a5508a897f4'
    let email = "";
    let fName = "";
    let lName = "";

    const options = {
        method: 'POST',
        headers: {Accept: 'application/json', 'Content-Type': 'application/json'},
        body: JSON.stringify({
            profiles: [
                {first_name: fName},
                {last_name: lName},
                {email: email}
            ]
        })
    };

    function postData() {
        if(email !=="") {
            fetch(klaviyo_API, options)
            .then(response => response.json())
            .then(response => console.log(response))
            .catch(err => console.error(err));    
        }      
    }
</script>

<section>
    <form on:submit|preventDefault={postData}>
        <label for="fname">First Name:</label>
        <input type="text" id="fname" name="fname" bind:value={fName}>

        <label for="lname">Last Name:</label>
        <input type="text" id="lname" name="lname" bind:value={lName}>

        <label for="email">Email:</label>
        <input type="text"  name="email" bind:value={email}>

        <button type=submit>Sign Up!</button>
    </form>
</section>

<style>
    section {
        background-color: var(--white);
        border-radius: 8px;
        color: var(--dark);
        padding: 1em;
        width: 85vw;
    }
    form {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 1em;
    }
</style>