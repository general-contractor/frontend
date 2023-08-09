<script>
    let contractor = {
        company: '',
        email: '',
        phoneNumber: '',
        description: '',
        bankInfo: '',
        photo: null
    };
    
    function signup() {
        // Handle signup logic here
    }
</script>

<form on:submit|preventDefault={signup}>
    <input type="text" bind:value={contractor.company} placeholder="Company Name" />
    <input type="email" bind:value={contractor.email} placeholder="Email" />
    <input type="tel" bind:value={contractor.phoneNumber} placeholder="Phone Number" />
    <textarea bind:value={contractor.description} placeholder="Description of Work"></textarea>
    <input type="text" bind:value={contractor.bankInfo} placeholder="Bank Info" />
    <input type="file" bind:files={contractor.photo} />
    <button type="submit">Sign Up</button>
</form>
