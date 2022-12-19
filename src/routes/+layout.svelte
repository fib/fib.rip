<script>
    import "../app.css";
    import { browser } from "$app/environment";
    import { onMount } from "svelte";

    onMount(() => {
        if (localStorage.getItem("darkTheme") == "true") {
            toggleTheme();
        }

        document.body.classList.remove("preload");
    });

    let themeEmoji = "🌚";

    function toggleTheme() {
        document.documentElement.classList.toggle("dark");

        const darkTheme = document.documentElement.classList.contains("dark");
        console.log(darkTheme);
        if (browser) localStorage.setItem("darkTheme", String(darkTheme));
        themeEmoji = darkTheme ? "🌞" : "🌚";
    }
</script>

<nav>
    <span id="title">fib.rip</span>
    <a class="navlink" href="https://github.com/fib">GitHub</a>
    <a class="navlink" href="mailto:mail@fib.rip">@</a>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <a class="navlink" id="themeButton" on:click={toggleTheme}>{themeEmoji}</a>
</nav>

<slot />

<style>
    nav {
        display: flex;
        align-items: flex-end;
        justify-content: right;
        position: relative;
        gap: 20px;
        width: 100%;
        margin-bottom: 40px;
    }

    nav > * {
        -webkit-touch-callout: none;
        -webkit-user-select: none;
        -khtml-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        user-select: none;
    }

    .navlink:hover {
        cursor: pointer;
    }

    #title {
        font-size: 24pt;
        font-weight: 600;
        margin-left: 0;

        position: absolute;
        top: 0;
        left: 0;
    }
</style>
