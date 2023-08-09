<script>
    let quotes = [
        // Sample data. In a real app, you'd fetch these from an API.
        {id: 1, description: 'Quote 1', status: 'accepted', date: '2023-08-01'},
        {id: 2, description: 'Quote 2', status: 'pending', date: '2023-08-05'},
        //... more quotes
    ];
    
    let searchTerm = '';
    let sortBy = 'date';
    let statusFilter = 'all';

    // Filter based on search term
    $: filteredQuotes = quotes.filter(quote => quote.description.toLowerCase().includes(searchTerm.toLowerCase()));

    // Sort based on sortBy criteria
    $: sortedQuotes = filteredQuotes.sort((a, b) => {
        if (sortBy === 'date') {
            return new Date(b.date) - new Date(a.date); // sort by newest first
        }
        // Add more sort conditions if required.
        return 0;
    });

    // Filter based on status
    $: displayedQuotes = sortedQuotes.filter(quote => statusFilter === 'all' || quote.status === statusFilter);
</script>

<input type="text" bind:value={searchTerm} placeholder="Search quotes..." />

<select bind:value={sortBy}>
    <option value="date">Sort by Date</option>
</select>

<select bind:value={statusFilter}>
    <option value="all">All</option>
    <option value="accepted">Accepted</option>
    <option value="pending">Pending</option>
</select>

{#each displayedQuotes as quote}
    <div>
        <h3>{quote.description}</h3>
        <p>Status: {quote.status}</p>
        <p>Date: {quote.date}</p>
    </div>
{/each}

<style>
    .quote-card {
        border: 1px solid #ccc;
        padding: 15px;
        margin-bottom: 15px;
    }
</style>
