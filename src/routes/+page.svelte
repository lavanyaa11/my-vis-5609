<script>
    let maxClick = 5;  // Default value
    let cnt = maxClick;

    function onClick() {
        if (cnt > 0) {
            cnt--;
        }
    }
</script>

<h1>Lavanya's VIS site</h1>

<div class="container">
    <img src="/Dog.jpg" alt="Funny Cat" width="300px" />

    <p>
        You can click up to 
        <select bind:value={maxClick} on:change={() => (cnt = maxClick)}>
            {#each [1, 2, 3, 4, 5] as optionNum}
                <option value={optionNum}>{optionNum}</option>
            {/each}
        </select>
        times
    </p>

    <button on:click={onClick} disabled={cnt === 0}>Click Me</button>

    {#if cnt > 0}
        <p>Remaining Number of Clicks: {cnt}</p>
    {/if}

    {#if cnt === 0}
        <p>No more clicks allowed</p>
    {/if}
</div>

<style>
    body {
        font-family: Arial, Helvetica, sans-serif;
        text-align: center;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    img {
        width: 300px;
        border-radius: 10px;
    }

    select {
        font-size: large;
        padding: 5px;
    }

    button {
        background-color: #44aa66;
        color: white;
        font-size: xx-large;
        padding: 10px 20px;
        border: none;
        cursor: pointer;
        border-radius: 5px;
        margin-top: 10px;
    }

    button:disabled {
        background-color: gray;
        cursor: not-allowed;
    }
</style>
