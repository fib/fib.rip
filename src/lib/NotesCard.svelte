<script>
    export let url;
    export let number;
    export let term;
    export let title;
</script>

<a class="card" href={url}>
    <div class="header">
        <span class="number">{number}</span>
        <span class="term">{term}</span>
    </div>
    <div class="card-title">
        <span class="class-title">{title}</span>
    </div>
</a>

<style>
    .card {
        background-color: var(--bg-color-secondary);
        color: var(--primary-color);
        border-radius: 5px;

        display: inline-block;

        padding: 10px 15px 15px;

        transition: all 0.3s ease-in-out;

        flex-grow: 1;
    }

    .card > * {
        -webkit-touch-callout: none;
        -webkit-user-select: none;
        -khtml-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }

    .card:hover {
        cursor: pointer;
        filter: brightness(120%);
    }

    .header {
        filter: opacity(50%);
        font-size: 80%;
    }

    .header:after {
        content: "\A";
        white-space: pre;
    }

    .number:after {
        content: " · ";
    }
</style>
