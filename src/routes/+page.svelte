<script lang="ts">
    let review_info:any = []
fetch('https://sheetdb.io/api/v1/p2lfv6hu1izi0?sheet=Reviews')
  .then((response) => response.json())
  .then((data) => review_info = data);
</script>
<main class="container-fluid">
    

    <article>
        <header>
            <h2 class="title is-2">About Me</h2>
        </header>
        <p>
            Hi, I am Maximillian Mata but I just go by Max. I graduated from UNLV with a Bachelor's degree in Mathematics and a Master's degree in Applied Statistics. I have been tutoring since 2019, I primarily specialize in higher level math starting with Algebra I / Geometry and going up to college level math and statistics. I have experience with both in-person and and virtual teaching / tutoring.
        </p>
    </article>
    
    <article>
        <header>
            <h2 class="title is-2">For New Students:</h2>
        </header>
        <div>
            <p>
                I am local to the Las Vegas area and am available for in-person tutoring or online tutoring. I have experience tutoring the following courses:
            </p>
            <ul class="list">
                <li >Pre-Algebra</li>
                <li >Algebra I / II</li>
                <li >Geometry</li>
                <li >Pre-Calc I / II</li>
                <li>Trigonometry</li>
                <li >AP Calculus AB / BC</li>
                <li >AP Statistics</li>
                <li >Calculus I / II / III</li>
                <li >Mathematical Statistics</li>
            </ul>
            <p>
                For inquiries on availability and pricing please email me at <a href="mailto:maxmata99@gmail.com">maxmata99@gmail.com</a> or text/call me at <a href="tel:702-478-0816">(702)-478-0816</a>
            </p>
        </div>
    </article>
    <article>
        <header>
            <h2>
                For Current Students:
            </h2>
        </header>
        <p>
            For those who I am currently tutoring, our session notes can be found in the student section under your ID and accessed with your student code. Practice material and quizzes for your class can be found within their respective pages.
        </p>
    </article>
    <article>
        <header>
            <hgroup>
                <h2>Reviews</h2>
                <p>The following are real reviews from real students. To submit your own review please go to the review page.</p>
            </hgroup>
        </header>
        {#each review_info as Reviews}
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
<style>
    
main{
    max-width: 95vw;
    margin-left: 2.5vw;
    margin-right: 2.5vw;
}    
ul{
    padding-left: 5vw;
}

</style>