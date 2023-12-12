<script>
    let articles = [
    {
        text: 'Stop plastic waste tips!',
        imgUrl: '/hippy-shuffle-4.jpg'
    },
    {
        text: 'Kies voor herbruikbare tassen',
        imgUrl: '/hippy-shuffle-1.jpg'
    },
    {
        text: 'Zeg vaker nee tegen eenmalige gebruiks verpakkingen',
        imgUrl: '/hippy-shuffle-2.jpg'
    },
    {
        text: 'Jaarlijks produceren mensen meer daan 400 miljoen ton aan plastic',
        imgUrl: '/hippy-shuffle-3.jpg'
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




<section class="hippy-cards">
    <div>
        <!-- on:click zet de functies back & next in werking -->
        <button on:click={back}>links</button>
        <button on:click={next}>rechts</button>
    </div>
    <svg viewBox="0 0 500 500">
        <path id="curve" fill="transparent" d="M73.2,148.6c4-6.1,65.5-96.8,178.6-95.6c111.3,1.2,170.8,90.3,175.1,97" />
        <text width="500">
          <textPath xlink:href="#curve">
             Peace and Love 
          </textPath>
        </text>
      </svg>
    
    <!-- deze foreach loop gaat de articles langs uit de js, i staat voor index, hierdoor krijgt de article die active is de class show -->
    {#each articles as article, i}
    <article class="z-index" class:show={i==active}>
                <h2>{article.text}</h2> 
        {#if article.imgUrl}
            <img src="{article.imgUrl}" alt="background hippy cards">
        {/if}
    </article>
    {/each}
</section>

<style>

    .hippy-cards{
        width:100%;
        height:100%;
        border-radius: 1rem;
        background-image: linear-gradient(red, orange, yellow, green, blue );
        background-size: 400% 400%;
        animation: hippy-background 10s linear infinite;
        display: grid;
        grid-template: 1fr/1fr "stack";
    }
    @keyframes hippy-background {
        0%{
            background-position: 10% 0%;
        }
        50%{
            background-position: 90% 100%;
        }
        100%{
            background-position: 10% 0%;
        }
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
        color:black;
    }
   
    img{
        position: absolute;
        top:0;
        width: 100%;
        height: 100%;
        border-radius: 1rem;
        opacity:.3;
    }

    /* circle animation */
    svg{
        position: absolute;
        animation: circle 10s linear infinite;
    }
    @keyframes circle{
        from{
            transform: rotate(0deg);
        }
        to{
            transform: rotate(360deg);
        }
    }   
    textPath{
        font-size: 3rem;
        animation:color-text 5s linear infinite;
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
        background-color: hotpink;
    }
    button:hover{
        cursor: pointer;
    }
</style>