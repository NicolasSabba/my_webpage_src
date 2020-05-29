<script>
</script>

<style>
    div.content {
        position: sticky;
        top: 120px;
        left: 10px;
        width: 270px;
        float: left;
        opacity: 0.5;
    }

    div.content:hover {
        opacity: 1;
    }

    div.content img.profile {
      border-radius: 50%;
      width: 150px;
      margin-left: 60px;
      margin-top: 10px

    }

    div.content p.description {
        padding: 5px;
        color: var(--text);
        text-align: center;
    }

    div.content h1.name {
        padding: 5px;
        color: var(--text);
        text-align: center;
    }

    div.content div.social{
        color: var(--text);
        text-align: center;
    }

    div.content div.social a{
        color: var(--text);
    }

    div.content div.social a:hover {
        color: var(--navbar-text-shadow);
    }

</style>

<div class="content">
    <img class="profile" src="https://pbs.twimg.com/profile_images/1244438560918384640/7yPACbDA_400x400.jpg" alt="ProfilePicture">
    <h1 class="name" >Nicolás</h1>
    <p class="description">
        Just another programmer with big dreams.
    </p>
    <div class="social">
        <a href="https://github.com/NicolasSabba" target="_blank">
            <i class="fab fa-github icon"></i>
            @NicolasSabba
        </a>
    </div>
    <div class="social">
        <a href="https://twitter.com/nico_sabba" target="_blank">
            <i class="fab fa-twitter"></i>
            @nico_sabba
        </a>
    </div>
    <div class="social">
        <a href="https://mateconbigote.itch.io/" target="_blank">
            <i class="fab fa-itch-io"></i>
            @MateConBigote
        </a>
    </div>
    <div class="social">
        <a href="https://www.instagram.com/nico.sabbatini/" target="_blank">
            <i class="fab fa-instagram"></i>
            @nico.sabbatini
        </a>
    </div>
</div>
