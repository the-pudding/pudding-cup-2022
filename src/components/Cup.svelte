<script>
    import copy from "$data/copy.json";
    console.log(copy.prelude);
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
        <p class="graf">{graf.value}</p>
    {/each}
    <!-- <ul>
        {#each copy.details as bullet}
        <li>{@html bullet.value}</li>
        {/each}
    </ul>
    <a href="https://forms.gle/wsBm4KTakWGKZzbY7" class="submit"><button>Submit</button></a>

    <p class="note">*{copy.commercial}</p> -->
</section>

<style>
    section {
        padding: 1rem 2rem;
        margin: 0 auto;
        max-width: 60rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        color: var(--color-gray-900);
    }

    .title-wrapper {
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

    .desc {
        font-family: var(--sans);
        font-size: var(--20px);
        margin: 0;
        text-align: center;
    }

    .prev-years {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: var(--sans);
        margin: 1rem 0;
    }

    .prev-years p {
        margin: 0 0.5rem 0 0;
        padding: 0 0 0.5rem 0;
        color: var(--color-gray-600);
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
        margin: 0 auto;
        font-family: var(--serif);
        line-height: 1.65;
        font-size: var(--16px);
    }

    .details ul {
        margin: 2rem 0;
        font-size: var(--16px);
        line-height: 1.65;
    }

    .details li {
        padding: 0.75rem 0;
        border-bottom: 1px solid var(--color-gray-200);
    }
      
     .submit {
        padding: 3rem 0;
        border-bottom: none;
     } 

     .submit button {
        background-color: var(--color-purple);
        color: var(--color-white);
        font-size: var(--22px);
        padding: 1rem 2rem;
        border-radius: 0.25rem;
     }

     .submit button:hover {
        background-color: var(--color-gray-900);
     }

     .note {
        max-width: 40rem;
        font-family: var(--sans);
        color: var(--color-gray-600);
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

        .graf, .details ul {
            font-size: var(--18px);
        }
	}
</style>