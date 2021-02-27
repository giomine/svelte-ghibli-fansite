<script>
    import Navbar from "./Navbar.svelte";

window.onload = () => {         // important! this defers the javascript so that all elements are created. its an alternatve to using defer.

    const app = document.getElementById('root')
    const logo = document.createElement('img')
    logo.src = 'logo.png'
    const container = document.createElement('div')
    container.setAttribute('class', 'container')

    fetch('https://ghibliapi.herokuapp.com/films')
      .then(res => res.json())
      .then(data => {
          console.log(data)
        data.forEach(film => {
            console.log(film.title)
            const card = document.createElement("div")
            card.setAttribute('class', 'card')

            const h1 = document.createElement('h1')
            h1.textContent = film.title 

            const p = document.createElement('p')
            p.setAttribute('class', 'pFilm')
            p.textContent = film.description

            container.appendChild(card)
            card.appendChild(h1)
            card.appendChild(p)

    })  

    app.appendChild(logo)
    app.appendChild(container)
})
.catch(error => {
    console.log(error)
})
}
</script>



<main>
    <h1><Navbar /> Ghibli Films</h1>
    <div id="root"></div>  
</main>



<style>
</style>