<script>
    import Navbar from "./Navbar.svelte";

window.onload = () => {         // important! this defers the javascript so that all elements are created. its an alternatve to using defer.

    const app = document.getElementById('root')
    const logo = document.createElement('img')
    logo.src = 'logo.png'
    const container = document.createElement('div')
    container.setAttribute('class', 'container')

    fetch('https://ghibliapi.herokuapp.com/people')
    .then(res => res.json())
    .then(data => {
        console.log(data);
        data.forEach((char) => {
            console.log(char.name + ", age " + char.age + ", is from " + char.films)

            const card = document.createElement("div")
            card.setAttribute('class', 'card')

            const h1 = document.createElement('h1')
            h1.textContent = char.name 

            const p = document.createElement('p')
            p.textContent = "Age: " + char.age

            const gender = document.createElement('p')
            gender.textContent = "Gender: " + char.gender

            const eyes = document.createElement('p')
            eyes.textContent = "Eye color: " + char.eye_color

            const hair = document.createElement('p')
            hair.textContent = "Hair color: " + char.hair_color

            const film = document.createElement('p')
            film.textContent = char.films

            container.appendChild(card)
            card.appendChild(h1)
            card.appendChild(p)
            card.appendChild(gender)
            card.appendChild(eyes)
            card.appendChild(hair)
            card.appendChild(film)

    })  

    app.appendChild(logo)
    app.appendChild(container)
})
.catch(error => {
    console.log('There has been a problem with your fetch operation: ', error)
})
}
</script>



<main>
    <h1><Navbar /> Ghibli Characters</h1>
    <div id="root"></div>  
</main>



<style>
    
</style>