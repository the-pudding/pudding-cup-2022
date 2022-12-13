<script>
    import copy from "$data/copy.json";
</script>

<section class="title-wrapper">
    <div class="prev-years">
        <p>Previous winners</p>
        <ul>
            {#each copy.years as year}
            <a href="{year.link}"><li>{year.year}</li></a>
            {/each}
        </ul>
    </div>
    <h1>{copy.title}</h1>
    <p class="desc">{copy.description}</p>
</section>
<section class="details">
    {#each copy.prelude as graf}
        <p class="graf">{@html graf.value}</p>
    {/each}
</section>

<section class="winners">
    <h2>The Winners</h2>
    <p class="graf">Our three favorite essays.</p>
    <ul>
        {#each copy.winners as winner}
            <li class="winner-block">
                <h5><a href={winner.url}>{winner.title}</a></h5>
                <p class="credit">By {@html winner.name}</p>
                <a href={winner.url}><img src="assets/images/{winner.img}.jpg" alt="{winner.alt}"/></a>
                {#each winner.remarks as graf}
                    <p class="graf">{@html graf.value}</p>
                {/each}
            </li>
        {/each}
    </ul>
</section>

<section class="honorable">
    <h2>Honorable Mentions</h2>
    <p class="graf">Definitely worth a click.</p>
    <ul>
        {#each copy.honorable as mention}
            <li class="mention-block">
                <h5><a href={mention.url}>{mention.title}</a></h5>
                <p class="credit">By {@html mention.name}</p>
            </li>
        {/each}
    </ul>
</section>

<style>
    a {
        cursor: pointer;
    }

    a:hover {
        color: var(--color-gray-600);
    }

    section {
        padding: 1rem;
        margin: 0 auto;
        max-width: 40rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        color: var(--color-gray-900);
    }

    .title-wrapper {
        max-width: 60rem;
        margin-bottom: 3rem;
    }

    h1 {
        font-family: var(--sans);
        font-weight: 700;
        font-size: var(--48px);
        text-align: center;
        line-height: 1.25;
        margin: 3rem 0 1rem 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        width: 100%;
    }

    img {
        margin: 1rem 0;
        width: 100%;
        border: 1px solid var(--color-gray-200);
    }

    img:hover {
        opacity: 0.75;
    }

    h2 {
        font-weight: 700;
        color: var(--color-gray-900);
        text-align: left;
        width: 100%;
        margin: 3rem 0 0 0;
        border-top: 1px solid var(--color-gray-200);
        padding: 1rem 0 0 0;
    }

    h5, h5 a {
        font-weight: 700;
        width: 100%;
        color: #a239ca;
        font-size: 1.25rem;
        margin: 0;
    }

    .desc {
        font-family: var(--sans);
        font-size: var(--20px);
        margin: 0;
        text-align: center;
    }

    .credit {
        font-family: var(--sans);
        font-size: 1.125rem;
        margin: 0.25rem 0;
        color: var(--color-gray-900);
    }

    :global(.credit a:hover) {
        color: #a239ca;
    }

    .prev-years {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: var(--sans);
        margin: 1rem 0;
        justify-content: center;
    }

    .prev-years p {
        margin: 0 0.5rem 0 0;
        padding: 0 0 0.5rem 0;
        color: var(--color-gray-600);
        min-width: 8rem;
    }

    .title-wrapper ul {
        display: flex;
        flex-direction: row;
        list-style: none;
        padding: 0;
    }

    .title-wrapper ul a {
        margin: 0 0.5rem;
        padding: 0;
        font-weight: 700;
        color: var(--color-gray-600);
    }

    .title-wrapper ul a:hover {
        color: var(--color-purple);
    }

    .title-wrapper li {
        padding: 0;
        margin: 0;
        line-height: 1;
    }

    .graf {
        max-width: 40rem;
        width: 100%;
        margin: 0 auto;
        font-family: var(--serif);
        line-height: 1.65;
        font-size: var(--16px);
        color: var(--color-gray-900);
    }

    :global(.graf a) {
        font-family: var(--sans);
        font-style: italic;
    }

    :global(.graf a:hover) {
        color: #a239ca;
    }

    .details {
        max-width: 40rem;
    }
    

    .mention-block {
        width: 100%;
        margin: 2rem 0 0 0;
    }

    .winner-block {
        width: 100%;
        margin: 4rem 0 0 0;
    }

    .honorable {
        margin: 0 auto 10rem auto;
    }

    @media only screen and (min-width: 30em) {
        h1 {
            font-size: var(--64px);
        }

        .prev-years {
            flex-direction: row;
        }

        .prev-years p {
            padding: 0;
        }

        .graf {
            font-size: var(--18px);
        }
    }
</style>