<script setup>

</script>

<template>
<header>
    <h1 class="text-gradient">NGUVU APP <i class="fas fa-dumbbell"></i></h1>
</header>
<main>
    <slot/>
</main>
<footer>
    <small>Created by </small>
    <a href="https://www.github.com/Kositany" target="_blank">
        <img src="https://avatars.githubusercontent.com/u/139861909?v=4" alt="pfp">
        <p>Kositany</p>
        <i class="fab fa-github"></i>
    </a>
</footer>
</template>

<style scoped>
header,
footer,
main{
    padding:1.2rem;
    width:100%;
    max-width: 680px;
    margin:0 auto;
}
main{
    flex:1;
}
footer{
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    padding: 3rem 0;
    padding-bottom: 1rem;
    justify-content: center;
    align-items: center;
}
footer a{
    text-decoration: none;
    display: flex;
    gap: 0.5rem;
    align-items: center;
    padding: 0.4rem;
    padding-right: 0.5rem;
    background: var(--background-muted);
    border-radius: 5rem;
    border: 1px solid transparent;
    transition-duration: 200ms;
    
}
footer a:hover{
    border-color: var(--color-link);
}
footer img{
    max-width: 30px;
    aspect-ratio: 1/1;
    border-radius: 50%;
}


</style>
