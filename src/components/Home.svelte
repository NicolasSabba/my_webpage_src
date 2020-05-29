<script>
    import Typewriter from 'svelte-typewriter'
	import { onDestroy } from 'svelte';

    let start_name = false;
    const interval = setInterval(() => {
        start_name = true;
        clearInterval(interval);
    }, 1000);

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
            '😍💓💕💖💗💘💝💞',
            'You are a handsome little bastard',
            '(づ￣ ³￣)づ I love you',
            'Yeet (╯°□°）╯︵ ┻━┻',
            '#TeamtTrees',
            'Error...',
            'No dessert for you',
            'Do you have McDonald´s money?',
            'You are a curious person... I like you',
            'SHAKESPEARE QUOTE OF THE DAY: An SSL error has occurred and a secure connection to the server cannot be made. "An SSL error has occured and a secure connection to the server , cannot be made"',
            'Send money',
            'You now have to send money',
            '🎶 That it´s a thriller, thriller night 🎶',
            '(☞ﾟヮﾟ)☞ Yaaaas',
            'ฅ^•ﻌ•^ฅ Meowwwww',
            '(•̀ᴗ•́)و ̑̑ This works',
            '(ง •̀_•́)ง Say that to my face',
            '"Spaghettiiii" ლ(ಠ_ಠლ)',
            '( ˘ ³˘)♥💕',
            '(~‾▿‾)~ It is my favourite song',
            '┬┴┬┴┤ ͜ʖ ͡°) ├┬┴┬┴ I know what are you doing',
            'HaVe YOu eVeR hAd a DrEAm?',
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
        min-width: 1100px; 
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
        animation: blink-caret 0.75s step-end 7;
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
        max-width: 60%;
        top: 223px;
        margin-left: 156px;
        opacity: 0.5;
    }

    div.content div.info {
        columns: 2;
        margin: auto;
        margin-top: 15px;
        width: 800px;
    }

    div.content div.info div.img {
        display: inline-block;
        width: 350px;
    }

    div.content div.info div.img img {
        border-radius: 50%;
        width: 350px;
    }

    div.content div.info div.text {
        padding-top: 75px;
        font-size: 20px; 
    }

    div.content div.info div.text p {
        color: var(--text);
        text-align: left;
        margin: auto;
    }

    div.content div.info div.text a {
        color: var(--text);
        text-decoration: underline;
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
    <div class="info">
        <div class="img">
            <img class="profile" src="https://pbs.twimg.com/profile_images/1244438560918384640/7yPACbDA_400x400.jpg" alt="ProfilePicture">
        </div>
        <div class="text">
            <p> Hi! I'm Nicolás Sabbatini.</p>
            <p> I am a very creative and passionate person.</p>
            <p> I like art and programming and I love matte colors.</p>
            <p> I am currently working at <a href="https://santexgroup.com/" target="_blank">Santex</a>,
                studying at <a href="https://www.famaf.unc.edu.ar/" target="_blank">Famaf</a>, and trying to fulfill my dreams.</p>
            <p> I really hope you like what you´ll find here.</p>
        </div>
    </div>
</div>
