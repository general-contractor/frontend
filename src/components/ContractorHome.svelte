<script>
    // Mock data, you would fetch this from your backend
    let requestedQuotesCount = 5; // replace with actual data from your backend
    let activeJobsCount = 3; // replace with actual data from your backend

    function goto(page) {
        // Handle routing logic here, e.g., using svelte-routing or another routing library.
    }
</script>

<div>
    <h1>Welcome, Contractor!</h1>
    <p>Requested Quotes: {requestedQuotesCount}</p>
    <p>Active Jobs: {activeJobsCount}</p>
    <button on:click={() => goto('quotes')}>View Quotes</button>
    <button on:click={() => goto('activeJobs')}>View Active Jobs</button>
</div>
