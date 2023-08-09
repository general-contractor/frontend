<script>
    import { onMount } from 'svelte';
    let userType = ''; // can be 'contractor' or 'customer'. Ideally, this should be fetched or determined based on login state.

    onMount(() => {
        // Mock logic to determine the user type. Replace this with actual logic.
        userType = 'contractor'; 
    });
</script>

<nav>
    {#if userType === 'contractor'}
        <a href="/contractor-home">Home</a>
        <a href="/contractor-quotes">Quotes</a>
        <a href="/contractor-jobs">Active Jobs</a>
        <a href="/contractor-settings">Settings</a>
        <a href="/contractor-invoices">Invoices</a>
    {:else if userType === 'customer'}
        <a href="/customer-home">Home</a>
        <a href="/customer-quotes">Quotes</a>
        <a href="/customer-jobs">Active Jobs</a>
        <a href="/customer-settings">Settings</a>
        <a href="/customer-invoices">Invoices</a>
    {/if}
</nav>

<style>
nav {
    display: flex;
    flex-direction: column;
    width: 200px;
    background-color: #f7f7f7;
    padding: 20px;
}

a {
    text-decoration: none;
    margin-bottom: 10px;
    color: black;
}
</style>
