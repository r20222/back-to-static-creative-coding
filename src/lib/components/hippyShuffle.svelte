<script>
    let articles = [
    {
        text: 'Stop plastic waste tips!',
        imgUrl: ''
    },
    {
        text: 'Kies voor herbruikbare tassen'
    },
    {
        text: 'Zeg vaker nee tegen eenmalige gebruiks verpakkingen'
    },
    {
        text: 'Jaarlijks produceren mensen meer daan 400 miljoen ton aan plastic'
    }
    ]
    let active = 0

    function next() {
        // controleer of de lengte van de articles niet al 3 is, want in dat geval is het volgende getal 0
        if(active != articles.length - 1){
            active = active + 1
        } else {
            active = 0
        }
    }

    function back() {
        // als active niet 0 is kan je er 1 vanaf trekken, als het wel 0 is dan ga je naar laatste article, nr 3
        if (active != 0) {
            active = active - 1;
        } else {
            active = articles.length - 1;
        }
    }

</script>




<section>
    <div>
        <!-- on:click zet de functies back & next in werking -->
        <button on:click={back}>links</button>
        <button on:click={next}>rechts</button>
    </div>
    <!-- deze foreach loop gaat de articles langs uit de js, i staat voor index, hierdoor krijgt de article die active is de class show -->
    {#each articles as article, i}
    <article class:show={i==active}>
        <h2>{article.text}</h2> 
    </article>
    {/each}
</section>

<style>
    section{
        width:100%;
        height:100%;
        background-color: blue;
        border-radius: 1rem;
        display: grid;
        grid-template: 1fr/1fr "stack";
    }
    section > * {
        grid-area: stack;
    }
    article{
        opacity: 0;

        &.show{
            opacity:1;
        }
    }
    h2{
        max-width: 50%;
        margin: 0 auto; /*voor horizontaal centreren*/
    }
    div{
        width:100%;
        height: 100%;
        /* background-color: yellow; */
        position: absolute;
        display:flex;
        justify-content: space-between;
        align-items: center;
    }
    button{
        width: 4rem;
        height:4rem;
        z-index: 100;
    }
    button:hover{
        cursor: pointer;
    }
</style>