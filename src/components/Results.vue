<template>
     <div class="search-holder">
        <p>visitor@christosad.github.io/terminal:~$ </p>
        <span class="old-command">{{filterCommand}}</span>
      </div>
    <div v-if="filterCommand === 'help'" class="answer results">
        <p><code>about</code><span>who am I? Learn more about me</span></p>
        <p><code>projects</code><span>see all projects I've created</span></p>
        <p><code>social</code><span>view my social profiles</span></p>
        <p><code>email</code><span>send me an email</span></p>
        <p><code>clear</code><span>clear previous results</span></p>
        <p><code>credits</code><span>credits must always be given</span></p>
    </div>
    <div v-else-if="filterCommand === 'about'" class="answer">
        <p>Hello, I'm Christos, a front-end developer specializing in website development since 2017. With a strong command of HTML, CSS, and JavaScript, I bring designs to life, creating visually captivating and user-friendly websites. I thrive in fast-paced environments, collaborating with cross-functional teams to deliver exceptional digital experiences. With a keen eye for detail and problem-solving skills, I am dedicated to crafting high-quality and impactful web solutions.</p>
    </div>
    <div v-else-if="filterCommand === 'projects'" class="answer results blue">
        <ul class="projects-list">
            <li><a href="https://cito.mecca.gr/" target="_blank"><code>Cito</code></a>Offers ready-to-eat gourmet food</li>
            <li><a href="https://villa-zoe.gr/" target="_blank"><code>Villa Zoe</code></a>Is a house at Pelion Greece</li>
            <li><a href="https://ilvief.gr/" target="_blank"><code>Ilvief</code></a>Expert in the areas of power distribution, power plant electrical installation, industrial automation and control</li>
            <li><a href="https://shoreditch.gr/" target="_blank"><code>Shoreditch</code></a>The coolest burger in town</li>
        </ul>
    </div>
    <div v-else-if="filterCommand === 'social'" class="answer results socials">
        <p><a href="https://github.com/christosad/" target="_blank"><coce>Github</coce></a>Visit my profile to view all the projects I've created</p>
        <p><a href="https://www.linkedin.com/in/christos-adamos-0ab3a2162/" target="_blank"><code>LinkedIn</code></a>See my background as a front-end developer</p>
    </div>
    <div v-else-if="filterCommand === 'credits'" class="answer results blue credits">
        <p><a href="https://fkcodes.com/" target="_blank"><code>ForrestKnight</code></a><span>for the inspiration</span></p>
        <p><a href="https://thenounproject.com/" target="_blank"><code>The ProjectNoun</code></a><span>for my iconlist</span></p>
        <p><a href="http://patorjk.com/software/taag/" target="_blank"><code>Patorjk</code></a><span>for the banner</span></p>
    </div>
    <div v-else class="answer">
        <p>Command not found. For a list of commands, type <code>help</code>.</p>
    </div>
   
</template>
<script>

export default {
    props: ['filterCommand']
}
</script>
<style scoped>
     p {
    color: #8DA101;
 }

 .search-holder {
    display: flex;
 }

 .answer {
    padding: 10px;
 }

 .answer.results code {
    min-width: 120px;
    display: inline-block;
    text-shadow: none;
    margin: 1.5px 0;
 }

 .answer ul {
    list-style-type: decimal;
    margin-left: 0;
    padding-left: 10px;
 }

 .answer span {
    color: var(--main-color);
 }

 .answer ul.projects-list li {
    font-size: 15px;
    font-family: var(--terminal-font);
    font-weight: 400;
 }

 .old-command {
    color: #8DA101;
    font-size: 15px;
    margin-left: 10px;
    font-family: var(--terminal-font);
    font-weight: 400;
 }

 .answer p {
    color: var(--main-color);
    max-width: 1200px;
 }

 .blue code {
    color: #7FBBB3;
 }

 .socials a {
    min-width: 120px;
    display: inline-block;
    color: #7FBBB3;
    text-decoration: none;
 }

 .answer.credits a code {
    min-width: 150px;
 }

</style>