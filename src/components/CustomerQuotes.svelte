<script>
    // Mock data, you would fetch this from your backend
    let quotes = [
        { id: 1, title: "Quote from XYZ Contractor", description: "Description here", status: "Pending" },
        //... add more quotes
    ];
</script>

<div>
    <h1>Your Quotes</h1>
    {#each quotes as quote}
    <div class="quote-card">
        <h2>{quote.title}</h2>
        <p>{quote.description}</p>
        <p>Status: {quote.status}</p>
    </div>
    {/each}
</div>

<style>
    .quote-card {
        border: 1px solid #ccc;
        padding: 15px;
        margin-bottom: 15px;
    }
</style>
