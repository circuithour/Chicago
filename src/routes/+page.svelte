<script>
    import { onMount } from "svelte";
    import Themeselector from "../lib/themeselector.svelte";
    let visible = false;

    function toggleVisible() {
        visible = !visible;
    }

    onMount(() => {
        const storedHue = localStorage.getItem("bg");
        document.querySelector("body").style.setProperty("--bg", storedHue);
    });
</script>

<main>
    <link
        rel="stylesheet"
        href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@48,300,0,200"
    />
    <div
        class="material-symbols-outlined"
        id="settings"
        on:click={toggleVisible}
    >
        settings
    </div>
    <div class="footer" />

    {#if visible}
        <Themeselector bind:visible />
    {/if}

    <div class="website">
        <div id="left">
            <div class="content" id="section1">
                <div class="header">
                    Breaking Boundaries: The Walter White Meth Company
                </div>
                <div>
                    Welcome to the captivating world of the Walter White Meth
                    Company, where chemistry meets crime in an unforgettable
                    journey through the drug trade. As the central character of
                    the critically acclaimed series "Breaking Bad," Walter
                    White, portrayed by Bryan Cranston, transformed from a
                    mild-mannered chemistry teacher into a ruthless drug lord.
                    The storyline, created by Vince Gilligan, revolves around
                    White's descent into the dark underworld of methamphetamine
                    production.
                </div>
            </div>
            <div class="content" id="section2">
                <div class="header">A Chemical Mastermind</div>
                <div>
                    At the heart of Walter White's meth empire lies his
                    exceptional knowledge of chemistry, which he harnesses to
                    create the purest and most sought-after blue methamphetamine
                    in the market. The series not only delves into the
                    complexities of the drug trade but also explores the moral
                    and ethical dilemmas faced by its characters. Walter White's
                    transformation from a man driven by desperation to one
                    motivated by power and ambition is a gripping narrative that
                    continues to captivate audiences worldwide.
                </div>
            </div>
            <div class="content" id="section3">
                <div class="header">Exploring Morality in the Underworld</div>
                <div>
                    Intrigue, suspense, and moral ambiguity are the cornerstones
                    of "Breaking Bad," and the Walter White Meth Company
                    perfectly encapsulates these elements. We invite you to
                    explore the world of chemistry, crime, and conscience
                    through the lens of one of television's most iconic
                    characters. Join us on a journey where the line between
                    right and wrong blurs, and the consequences of one's choices
                    are felt deeply. Welcome to the Walter White Meth Company,
                    where the legacy of a chemistry teacher turned drug lord
                    continues to enthrall and challenge our understanding of
                    morality and human nature.
                </div>
            </div>
        </div>
        <div id="right">
            <div id="trailer">
                <iframe
                    width="560"
                    height="315"
                    src="https://www.youtube.com/embed/HhesaQXLuRY?si=ud95i2Wkf0qzobN8"
                    title="YouTube video player"
                    frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                    allowfullscreen
                />
            </div>
        </div>
    </div>
    <!-- svelte-ignore a11y-missing-attribute -->
</main>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Inter&display=swap");
    @font-face {
        font-family: break-bad;
        src: url("../lib/Helvetica 93 Black Extended.otf");
    }

    .header {
        font-weight: bold;
        border-bottom: solid 2px #ffffff3a;
        width: 100%;
        font-size: 38px;
        font-family: break-bad, sans-serif;
        line-height: 27px;
        margin-bottom: 1rem;
    }
    .website {
        margin-top: 60px;
        display: flex;
        flex-direction: row;
        color: white;
        font: sans-serif;
        height: 100svh;
        width: 100svw;
    }

    #section1 {
        display: flex;
        flex: 33% 0% 0%;
        height: 100vh;
        text-align: left;
    }

    #section2 {
        display: flex;
        flex: 0% 33% 0%;
        height: 100vh;
        text-align: right;
    }

    #section3 {
        display: flex;
        flex: 0% 0% 33%;
        height: 100vh;
        text-align: left;
    }

    .content {
        display: flex;
        flex-direction: column;
        padding: 1rem;
        line-height: 2rem;
        font-family: "Inter", sans-serif;
        line-height: 20px;
    }
    .footer {
        position: absolute;
        bottom: 0;
        border-right: 100vw solid hsl(var(--bg), 50%, 13%);
        border-bottom: 50vh solid hsl(var(--bg), 50%, 10%);
        z-index: -1;
    }

    .material-symbols-outlined {
        font-variation-settings: "FILL" 0, "wght" 200, "GRAD" -25, "opsz" 48;
        color: white;
        font-size: 50px;
    }

    #settings {
        display: inline-block;
        position: fixed;
        top: 8px;
        left: 8px;
        user-select: none;
    }

    #settings:hover {
        cursor: pointer;
    }

    #trailer {
        display: inline-block;
        float: right;
    }

    #left {
        display: flex;
        flex-direction: column;

        width: 50%;
    }

    #right {
        display: flex;

        margin: auto;
        width: 50%;
    }
</style>
