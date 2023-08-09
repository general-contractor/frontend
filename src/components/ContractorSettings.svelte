<script>
    // Sample data for a contractor.
    let contractor = {
        bankInfo: "Bank XYZ, Account 123456",
        workDescription: "General Contractor, specializes in residential projects.",
        photo: "path_to_image.jpg",
        companyName: "BuildItRight Inc.",
        phoneNumber: "123-456-7890",
        email: "contractor@email.com"
    };

    let editMode = false;
    let files; // Declare files here

    function toggleEditMode() {
        editMode = !editMode;
    }

    function saveChanges() {
        // Send the updated `contractor` data to your backend to save changes.
        toggleEditMode();
    }

    // Watch for file changes and update the photo
    $: if (files && files[0]) {
        const reader = new FileReader();
        reader.onload = (e) => {
            contractor.photo = e.target.result;
        };
        reader.readAsDataURL(files[0]);
    }
</script>

<section>
    {#if !editMode}
        <img src={contractor.photo} alt="Contractor Photo" width="100">
        <h2>{contractor.companyName}</h2>
        <p>{contractor.workDescription}</p>
        <p>Phone: {contractor.phoneNumber}</p>
        <p>Email: {contractor.email}</p>
        <p>Bank Info: {contractor.bankInfo}</p>
        <button on:click={toggleEditMode}>Edit</button>
    {:else}
        <input type="file" bind:files={files} />
        <label>
            Company Name:
            <input type="text" bind:value={contractor.companyName} />
        </label>
        <label>
            Work Description:
            <textarea bind:value={contractor.workDescription}></textarea>
        </label>
        <label>
            Phone:
            <input type="text" bind:value={contractor.phoneNumber} />
        </label>
        <label>
            Email:
            <input type="email" bind:value={contractor.email} />
        </label>
        <label>
            Bank Info:
            <input type="text" bind:value={contractor.bankInfo} />
        </label>
        <button on:click={saveChanges}>Save Changes</button>
        <button on:click={toggleEditMode}>Cancel</button>
    {/if}
</section>

<style>
/* Basic styles for structure. */
section {
    width: 60%;
    margin: 0 auto;
    border: 1px solid #ccc;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

label {
    display: block;
    margin-bottom: 10px;
}

button {
    margin-right: 10px;
}
</style>
