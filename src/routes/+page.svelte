<script>
    import NotesCard from "$lib/NotesCard.svelte";
    import Layout from "./+layout.svelte";

    let notes = [
        {
            url: "https://gh.fib.rip/lecture-notes/cs220/notes.pdf",
            number: "CS220",
            term: "Fall 2022",
            title: "Applied Discrete Math",
        },
    ];
</script>

<p>Computer science student based in Boston, Massachusetts.</p>

<div id="notes">
    <div id="notes-header">
        <header id="notes-title">Lecture Notes</header>
        <span class="text-light"
            >(see <a href="https://gh.fib.rip/lecture-notes/LICENSE.txt"
                >LICENSE</a
            >)</span
        >
    </div>
    {#each notes as note}
        <NotesCard {...note} />
    {/each}
</div>

<style>
    #notes {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        justify-content: space-between;
    }

    #notes-header {
        margin-bottom: 10px;
        flex-basis: 100%;
    }

    #notes-title {
        margin-right: 5px;
        display: inline-block;
        font-weight: bold;
    }
</style>
