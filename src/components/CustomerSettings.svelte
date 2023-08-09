<script>
    let customerInfo = {
        name: '',
        phoneNumber: '',
        email: '',
        address: ''
    };

    function updateCustomerInfo() {
        // Logic to update customer info, e.g., make an API call to update.
    }
</script>

<div>
    <h1>Settings</h1>
    
    <input type="text" bind:value={customerInfo.name} placeholder="Name" />
    <input type="tel" bind:value={customerInfo.phoneNumber} placeholder="Phone Number" />
    <input type="email" bind:value={customerInfo.email} placeholder="Email" />
    <input type="text" bind:value={customerInfo.address} placeholder="Address" />
    
    <button on:click={updateCustomerInfo}>Update Information</button>
</div>
