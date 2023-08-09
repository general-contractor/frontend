<script>
    import { Router, Route } from "svelte-routing";
    import SideNavbar from './components/SideNavbar.svelte';
    
    // Importing all your components for routing
    import ContractorHome from './components/ContractorHome.svelte';
    import ContractorQuotes from './components/ContractorQuotes.svelte';
    import ContractorActiveJobs from './components/ContractorActiveJobs.svelte';
    import ContractorSettings from './components/ContractorSettings.svelte';
    import ContractorInvoices from './components/ContractorInvoices.svelte';
    import CustomerHome from './components/CustomerHome.svelte';
    // ... similarly import other customer components
</script>

<div class="app-container">
    <SideNavbar />
    
    <div class="main-content">
        <Router>
            <Route path="/contractor-home" component={ContractorHome} />
            <Route path="/contractor-quotes" component={ContractorQuotes} />
            <Route path="/contractor-jobs" component={ContractorActiveJobs} />
            <Route path="/contractor-settings" component={ContractorSettings} />
            <Route path="/contractor-invoices" component={ContractorInvoices} />
            <Route path="/customer-home" component={CustomerHome} />
        </Router>
    </div>
</div>

<style>
.app-container {
    display: flex;
}

.main-content {
    flex: 1;
    padding: 20px;
}
</style>
