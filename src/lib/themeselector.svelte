<script>
    export let visible;
    const storedHue = localStorage.getItem("bg");
    let hue = storedHue;

    function saveTheme() {
        localStorage.setItem("bg", hue);
        document.querySelector("body").style.setProperty("--bg", hue);
        visible = false;
    }
</script>

<div class="backdrop">
    <div class="container">
        <div id="content">
            <p>Please choose a hue.</p>
            <span style="color: hsl({hue}, 50%, 15%)">{hue}</span>
            <input
                type="range"
                min="0"
                max="255"
                id="slider"
                bind:value={hue}
            />
            <br />
            <button id="save" on:click={saveTheme}>Save</button>
        </div>
    </div>
</div>

<style>
    @import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

    .backdrop {
        background-color: rgba(0, 0, 0, 0.295);
        display: flex;
        height: 100vh;
        width: 100vw;
        animation: fadein 0.2s ease-in-out;
    }

    @keyframes fadein {
        0% {
            opacity: 0;
        }

        100% {
            opacity: 100;
        }
    }
    .container {
        display: flex;
        width: 400px;
        height: 150px;
        padding: 1rem;
        margin: auto;
        background-color: rgba(0, 0, 0, 0.199);
        flex-direction: column;
        color: white;
        border-radius: 15px;
        font-family: "Roboto", sans-serif;
        text-align: center;
        justify-content: center;
        font-weight: 500;
        align-items: center;
        animation: flyin 0.3s ease-in-out;
    }

    @keyframes flyin {
        0% {
            transform: scale(50%);
        }

        100% {
            transform: scale(100%);
        }
    }

    #save {
        border: solid 1px hsl(var(--bg), 65%, 15%);
        border-radius: 6px;
        background-color: #ffffff10;
        width: 100px;
        height: 30px;
        font-family: "Roboto", sans-serif;
        font-weight: 200;
        color: white;
        text-align: center;

        align-items: center;
    }

    #content {
        display: flex;
        flex-direction: column;
        line-height: 30px;
        align-items: center;
        gap: 5px;
    }

    p {
        margin: 0;
    }
</style>
