<h1>Mysterious baroque minimalist atmosphere</h1>

<!-- vierkant met inhoud -->
<section class="square">
    <!-- deur -->
    <section class="door">
        <section class="pillars">
            <section class="cirkle"></section>
            <section class="cover-up"></section>
        </section>

        <section class="pillars">
            <section class="cirkle"></section>
            <section class="cover-up"></section>
        </section>

        <section class="pillars">
            <section class="cirkle"></section>
            <section class="cover-up"></section>
        </section>
    </section>

    <section class="floor">
        <section class="shadow-of-pillars">
            <section class="pillar-shadow"></section>
            <section class="pillar-shadow"></section>
            <section class="pillar-shadow"></section>


        </section>
    </section>
</section>

<style>
    .square{
        width:50vw;
        height:80vh;
        background-image: linear-gradient(oklch(49.97% 0 0), oklch(75.25% 0 0),  oklch(97.87% 0 6.99));
        overflow: hidden;
    }
    .door{
        width:20rem;
        height:25rem;
        background-color: oklch(77.44% 0.003 165.05);
        box-shadow: oklch(69.66% 0.003 286.32) 0rem 0rem 0rem .8rem;
        border-radius: 30rem 30rem 0rem 0rem;
        margin:auto;
        position: relative;
        top:2rem;
        overflow: hidden;
        display: flex;
        gap: 2rem;
    }
    .floor{
        width:100%;
        height: 100%;
        background-image: linear-gradient(oklch(29.72% 0 0), oklch(59.99% 0 0),oklch(29.72% 0 0));
        position: relative;
        top:2rem;
    }
    .pillars{
        min-width:12rem;
        height:25rem;
        background-color: black;
        border-radius: 30rem 30rem 0rem 0rem;
        /* box-shadow: oklch(69.66% 0.003 286.32) 0rem 0rem 0rem .8rem; */

        /* margin:auto; */
        position: relative;
        animation: pillars 5s linear infinite;
        top:5rem;
    }
    @keyframes pillars{
        0%{
            right:0rem;
        }
        100%{
            right:14rem;
        }
    }
    .cirkle{
        width: 12rem;
        height:7rem;
        background-color: black;
        box-shadow: oklch(70% 0.003 286.32) 0rem 0rem 0rem .8rem;
        border-radius: 100px 100px 0% 0%;
    }
    .cover-up{
        width: 12rem;
        height:10rem;
        background-color: black;
        position: relative;
        top:0rem;
    }


    /* floor */
    .shadow-of-pillars{
        width:20rem;
        height:35rem;
        margin:auto;
        background-color: transparent;
        display: flex;
        gap: 12rem;
        overflow: hidden;
        /* transform: perspective(1rem) rotateX(1deg); */
        /* position: relative; */
        /* left: 4.5rem */
        /* animation: pillars 5s linear infinite; */
        /* box-shadow: .1rem 2rem 3rem white; */
    }
    .pillar-shadow{
        min-width:2rem;
        height:100%;
        background-color: white;
        /* box-shadow: 1rem 1rem 10rem 2rem white; */
        filter: blur(2rem);
        position: relative;
        right:2rem; 
        animation: pillars-shadow 5s linear infinite;

    }
    @keyframes pillars-shadow{
        0%{
            right:2rem;
        }
        100%{
            right:16rem;
        }
    }
   
</style>