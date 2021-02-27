<script>
    import Navbar from "./Navbar.svelte";
</script>

<main>
    <h1><Navbar /> Hello Ghibli Fans!</h1>
    <div class="contain">
        <div class="text-contain">
            <p>Welcome to the hub for all things Ghibli.</p>
            <p>Where would you like to go?<br>Navigate using the links at the top!</p>
        </div>
        <img src="../logo.png" alt="ghibli logo">
    </div>
</main>

<style>
    .contain {
        height: 70vh;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
    }

    p {
        margin: 0 auto;
    }
</style>