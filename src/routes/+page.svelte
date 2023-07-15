<script>
    import "$lib/styles/global.css";
    import profilePhoto from "$lib/images/profile_rehan.jpg";
    import arrowDown from "$lib/images/arrow_down.png";
    import Chill from "$lib/components/Chill.svelte";

    function scrollIntoView({ target }) {
        const el =
            target.id === "arrow_img"
                ? document.querySelector("#Blogs")
                : document.querySelector(target.getAttribute("href"));
        if (!el) return;
        el.scrollIntoView({
            behavior: "smooth",
        });
    }
</script>

<svelte:head>
    <title>Rayhan's Portfolio</title>
    <meta name="description" content="Rayhan's Portfolio">
</svelte:head>

<main class="app">
    <section class="bio">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src={profilePhoto} alt="Profile Photo" />
        <div class="bio_text">
            <h2>Hi, I'm Rayhan!</h2>
            <h4>
                I have a bachelor degree on information system, this is where I
                post my projects & other stuffs! Sorry for my bad English, I'm
                still learning to be better about it :)
            </h4>
            <h4>
                You also can find me in my <a
                    id="linked_in"
                    href="https://www.linkedin.com/in/rayhan-an-hidayat"
                    target="_blank">LinkedIn</a
                > or <a id="github" href="https://github.com/RayhanHidayat" target="_blank">GitHub</a> account.
            </h4>
        </div>
    </section>
    <div class="arrow_down">
        <a
            id="arrow_click"
            href="#Blogs"
            on:click|preventDefault={scrollIntoView}
        >
            <img id="arrow_img" src={arrowDown} alt="Arrow Down" />
        </a>
    </div>
    <section id="Blogs" class="blogs">
        <Chill />
        <h4>there is nothing here, right now :) until then... goodbye 👋</h4>
    </section>
</main>

<style>
    .app {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
    }
    .bio {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-evenly;
        align-items: center;
        min-height: 90vh;
    }
    .arrow_down {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 10vh;
    }
    .bio_text {
        display: flex;
        flex-direction: column;
        max-width: 40vw;
    }
    .blogs {
        display: flex;
        flex-direction: column;
        gap: 3rem;
        height: 100vh;
        justify-content: center;
        align-items: center;
    }
    #linked_in, #github {
        color: #11bfae;
        text-decoration: none;
    }
    #linked_in:active, #github:active {
        color: rgba(17, 191, 174, 0.5);
    }
    #linked_in:hover, #github:hover {
        animation-name: hover_link;
        animation-duration: 1s;
        border-bottom: 3px solid;
    }
    #arrow_click {
        transition: transform 0.2s;
    }
    #arrow_img {
        width: 2em;
        height: 2em;
    }
    #arrow_click:hover {
        -ms-transform: scale(1.5);
        -webkit-transform: scale(1.5);
        transform: scale(1.5);
    }
    @keyframes hover_link {
        from {
            border-color: rgba(17, 191, 174, 0);
        }
        to {
            border-color: rgba(17, 191, 174, 1);
        }
    }

    img {
        width: 15em;
        height: 15em;
        border-radius: 50%;
    }
    h2 {
        color: #11bfae;
    }

    @media (max-width: 800px) {
        .bio {
            flex-direction: column;
        }
        img {
            width: 10em;
            height: 10em;
        }
        h2 {
            text-align: center;
            font-size: 20px;
        }
        h4 {
            text-align: center;
            font-size: 15px;
        }
    }
</style>
