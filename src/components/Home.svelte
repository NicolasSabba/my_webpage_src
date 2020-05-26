<script>
    import Typewriter from 'svelte-typewriter'
	import { onDestroy } from 'svelte';

    let start_name = false;
    const interval = setInterval(() => {
        start_name = true;
        clearInterval(interval);
    }, 3000);

    onDestroy(() => clearInterval(interval));

    let start_random = false;
    let show_random = false;
    let random_phrase;
    function load_random_phrase() {
        // TODO More!!!!
        const rp = [
            'Is this working?',
            'I´m Commander Shepard and this is my favorite webpage on the Citadel.',
            'This is not a beach this is a webpage.',
            'Is this thing on?',
            'This is in fact not Minecraft.',
            '01001110 01100101 01110010 01100100',
        ];
        random_phrase = rp[Math.floor(Math.random() * rp.length)];
        start_random = true;
    }

</script>
<style>
    div.content {
        width: 100%;
        height: 100%;
    }

    div.content div.terminal{
        margin: auto;
        margin-top: 10px; 
        width: 98%;
        height: 400px;
        background-color: #333;
        border: 1px solid var(--background-shadow-2);
        border-radius: 10px;
    }

    div.content div.terminal p.const{
        color: var(--text);
        font-size: 55px;
        float: left;
        margin-left: 55px;
        margin-right: 27px;
    }

    div.content div.terminal p.name{
        color: var(--text);
        font-size: 55px;
        float: left;
    }

    div.content div.terminal p.cursor {
        color: transparent;
        font-size: 55px;
        text-align: left;
        float: left;
        margin-left: 0px;
        animation: blink-caret 0.75s step-end 10;
    }

    @keyframes blink-caret {
        from, to { color: transparent; } 
        50% { color: var(--text); }
    }

    div.content div.terminal p.load-text {
        color: var(--text);
        font-size: 20px;
        position: absolute;
        top: 200px;
        margin-left: 156px;
        opacity: 0.5;
    }

    div.content div.terminal p.load-bar {
        color: var(--text);
        font-size: 20px;
        position: absolute;
        top: 200px;
        left: 400px;
        opacity: 0.5;
    }

    div.content div.terminal p.random-text {
        color: var(--text);
        font-size: 20px;
        position: absolute;
        top: 223px;
        margin-left: 156px;
        opacity: 0.5;
    }

</style>

<div class="content">
    <div class="terminal">
        <p class="const">$ ></p>
        {#if start_name}
            <Typewriter interval={250} cursor={false} on:done={load_random_phrase}>
                <p class="name"> HI!, I AM NICOLÁS</p>
            </Typewriter>
        {/if}
        <p class="cursor">_</p>
        {#if start_random}
            <p class="load-text">Loading random phrases:</p>
            <Typewriter interval={250} cursor={false} on:done={()=> show_random = true}>
                <p class="load-bar">====================|</p>
            </Typewriter>
            #{#if show_random}
                <p class="random-text">Done!</p>
                <p class="random-text" style="top: 269px;"> {random_phrase} </p>
            {/if}
        {/if} 
    </div>
    <h1>Esto es el home</h1>
</div>
