<script>
    // Mock data, you would fetch this from your backend
    let activeJobs = [
        { id: 1, title: "Job with XYZ Contractor", description: "Description here", startDate: "2023-08-07" },
        //... add more jobs
    ];
</script>

<div>
    <h1>Your Active Jobs</h1>
    {#each activeJobs as job}
    <div class="job-card">
        <h2>{job.title}</h2>
        <p>{job.description}</p>
        <p>Start Date: {job.startDate}</p>
    </div>
    {/each}
</div>

<style>
    .job-card {
        border: 1px solid #ccc;
        padding: 15px;
        margin-bottom: 15px;
    }
</style>
