<script>
    let isLogin = true;
    let customer = {
        name: '',
        phoneNumber: '',
        email: '',
        address: ''
    };

    function toggleAuthMode() {
        isLogin = !isLogin;
    }

    function handleAuth() {
        if(isLogin) {
            // Handle login logic
        } else {
            // Handle register logic
        }
    }
</script>

<div>
    <h1>{isLogin ? 'Customer Login' : 'Customer Register'}</h1>

    {#if !isLogin}
        <input type="text" bind:value={customer.name} placeholder="Name" />
        <input type="text" bind:value={customer.address} placeholder="Address" />
    {/if}
    <input type="email" bind:value={customer.email} placeholder="Email" />
    <input type="tel" bind:value={customer.phoneNumber} placeholder="Phone Number" />
    
    <!-- Typically you'll also have password fields, but they are omitted for brevity -->

    <button on:click={handleAuth}>{isLogin ? 'Login' : 'Register'}</button>
    <p on:click={toggleAuthMode}>
        {isLogin ? 'Need an account? Register' : 'Already have an account? Login'}
    </p>
</div>
