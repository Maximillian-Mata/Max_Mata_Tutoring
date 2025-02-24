<script lang="ts">
    
    //Fetching data from google sheet
    

let spreadsheet_info:any = []
fetch('https://sheetdb.io/api/v1/p2lfv6hu1izi0?sheet=Reviews')
  .then((response) => response.json())
  .then((data) => spreadsheet_info = data);
//Writing to the sheet

/*
let example_review = [{'Submitter': 'third person', 'Review': "here", 'Approved': 'FALSE'}]
fetch('https://sheetdb.io/api/v1/p2lfv6hu1izi0?sheet=Reviews', {
    method: 'POST',
    headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        data: example_review
    })
})
  .then((response) => response.json())
  .then((data) => console.log(data));*/



  let reviewer_info: {Submitter: string, Review: string, Approved: string}[] = [{'Submitter':'', 'Review':'', 'Approved':'FALSE'}]
  function SubmitReview(){
    fetch('https://sheetdb.io/api/v1/p2lfv6hu1izi0?sheet=Reviews', {
    method: 'POST',
    headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json'
    },
    body: JSON.stringify({
        data: reviewer_info
    })
})
  .then((response) => response.json())
  .then((data) => {
    console.log(data)
    reviewer_info = [{'Submitter':'', 'Review':'', 'Approved':'FALSE'}]
});
  }
</script>
<main class="container-fluid">
    <h2>Submit a Review</h2>
    <article>
        <form>
            <fieldset>
                <label>
                    Name:
                    <input placeholder="Full Name"
                    autocomplete="given-name" bind:value={reviewer_info[0].Submitter}/>
                </label>
                <label>
                    Review:
                    <textarea
                    placeholder="Write a review of your experience"
                    bind:value={reviewer_info[0].Review}></textarea>
                </label>
            </fieldset>
            <button on:click={SubmitReview}>Submit</button>
        </form>
    </article>
    <article>
        <header>
            <h2>Real Reviews</h2>
        </header>
        {#each spreadsheet_info as Reviews}
        {#if Reviews.Approved == "TRUE"}
            <blockquote>
                {Reviews.Review}
                <footer>
                    <cite>- {Reviews.Submitter}</cite>
                </footer>
            </blockquote>
        {/if}
        {/each}
    </article>
</main>
