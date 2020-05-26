<script>
    export let active;

    function change_active(value) {
        console.log(active, window.location.href.split('/#/'))
        active = value;
    }

</script>

<style>
    nav {
        padding: 0;
        margin: 0;
        width: 100%;
        background-color: var(--navbar-color); 
        height: 65px;
        font-weight: bold;
        font-size: 29px;
    }

    nav a.link {
        padding: 0px;
        margin: 18px;
        float: right;
    }
    
    nav a.link.active {
        color: var(--text);
    }

    nav a.link.active:hover {
        color: var(--navbar-text-shadow);
        cursor: pointer;
    }

    nav a.link.inactive {
        color: var(--navbar-text-shadow);
    }

    nav a .home {
        padding: 0px;
        margin: 18px;
        stroke: var(--text);
        float: left;
        height: 29px;
        width: 29px;
        fill: none;
        stroke-linecap: round;
        stroke-linejoin: round;
        stroke-width: 50px;
    }

    nav a .home.active {
            stroke: var(--text);
    }

    nav a .home:hover.active {
        stroke: var(--navbar-text-shadow);
        cursor: pointer;
    }

    nav a .home.inactive {
        stroke: var(--navbar-text-shadow);
    }

</style>

<nav>
    <a href="/#">
        <svg width='512' height='512' viewBox='0 0 512 512' class='home {active === "/" || active === "/#" ? "inactive" : "active"}' on:click='{() => change_active("/#")}'>
            <title>ionicons-v5-i</title>
            <path d='M80,212V448a16,16,0,0,0,16,16h96V328a24,24,0,0,1,24-24h80a24,24,0,0,1,24,24V464h96a16,16,0,0,0,16-16V212'/>
            <path d='M480,256,266.89,52c-5-5.28-16.69-5.34-21.78,0L32,256'/>
            <polyline points='400 179 400 64 352 64 352 133'/>
        </svg>
    </a>
    <a href="#/blog" class='link {active === "#/blog" ? "inactive" : "active"}' on:click='{() => change_active("blog")}'>Blog</a>
    <a href="#/showcase" class='link {active === "#/showcase" ? "inactive" : "active"}' on:click='{() => change_active("showcase")}'>Showcase</a>
    <a href="#/projects" class='link {active === "#/projects" ? "inactive" : "active"}' on:click='{() => change_active("projects")}'>Projects</a>
    <a href="#/me" class='link {active === "#/me" ? "inactive" : "active"}' on:click='{() => change_active("me")}'>About me</a>
</nav>
