<script>
    export let active;

    function change_active(value) {
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
        border-bottom: 2px solid var(--background-shadow-1);
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
</style>

<nav>
    <a href="/#" class='link {active === "/" || active === "/#" ? "inactive" : "active"}' style="float: left" on:click='{() => change_active("/#")}'>
        <i class="fas fa-home"></i>
    </a>
    <!--
    <a href="#/blog" class='link {active === "#/blog" ? "inactive" : "active"}' on:click='{() => change_active("blog")}'>Blog</a>
    <a href="#/showcase" class='link {active === "#/showcase" ? "inactive" : "active"}' on:click='{() => change_active("showcase")}'>Showcase</a>
    <a href="#/projects" class='link {active === "#/projects" ? "inactive" : "active"}' on:click='{() => change_active("projects")}'>Projects</a>
    -->
    <a href="#/me" class='link {active === "me" ? "inactive" : "active"}' on:click='{() => change_active("me")}'>About me</a>
</nav>
