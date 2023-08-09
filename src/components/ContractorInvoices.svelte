<script>
    // Mock data, you would fetch this from your backend
    let invoices = [
        { id: 1, amount: 1200, dueDate: "2023-08-20", status: "Unpaid" },
        //... add more invoices
    ];

    function sendInvoice(id) {
        // Handle logic to send invoice, e.g., make an API call.
    }
</script>

<div>
    <h1>Invoices</h1>
    {#each invoices as invoice}
    <div class="invoice-card">
        <h2>Invoice #{invoice.id}</h2>
        <p>Amount: ${invoice.amount}</p>
        <p>Due Date: {invoice.dueDate}</p>
        <p>Status: {invoice.status}</p>
        {#if invoice.status === 'Unpaid'}
        <button on:click={() => sendInvoice(invoice.id)}>Send Invoice</button>
        {/if}
    </div>
    {/each}
</div>

<style>
    .invoice-card {
        border: 1px solid #ccc;
        padding: 15px;
        margin-bottom: 15px;
    }
</style>
