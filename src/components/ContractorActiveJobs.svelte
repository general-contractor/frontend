<script>
    // Mock data, you would fetch this from your backend
    let activeJobs = [
        { id: 1, title: "Job for ABC Corp", description: "Description here", startDate: "2023-08-07" },
        //... add more jobs
    ];

    function completeJob(id) {
        // Handle logic to mark a job as complete, e.g., make an API call to update the status.
    }
</script>

<div>
    <h1>Active Jobs</h1>
    {#each activeJobs as job}
    <div class="job-card">
        <h2>{job.title}</h2>
        <p>{job.description}</p>
        <p>Start Date: {job.startDate}</p>
        <button on:click={() => completeJob(job.id)}>Mark as Complete</button>
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
