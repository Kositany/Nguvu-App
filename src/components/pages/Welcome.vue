<script setup>
    defineProps({
        handleChangeDisplay: Function
    })
</script>

<template>

<section id="welcome">
    <div class="benefits">
        <h2>Complete this program <br>if you want to...</h2>
        <div>
            <p>✅ Follow a simple program with proven results.</p>
            <p>✅ Get Fit, Healthy, Strong and absolutely Shredded.</p>
            <p>✅ Learn more about gym , training and technique.</p>
        </div>
    </div>
    <div>
            <h3>Training Plan</h3>
            <p>This training plan follows a structures known as the <strong>Bro Split</strong>.</p>
            <h5><i>Push &rarr; Pull &rarr; Legs &rarr; Repeat</i></h5>
    </div>
    <div class="card || challenge">
        <h3>🔥 Your Challenge</h3>
        <p>Complete all workouts and track your progress</p>
        <p>Do you Accept? 💪🏽</p>
        <button @click="()=>handleChangeDisplay(2)">BEGIN &rarr;</button>
    </div>
</section>


</template>

<style scoped>
#welcome,
.challenge,
.benefits{
    display: flex;
    flex-direction: column;
}
#welcome{
    gap:1.5rem;
}
.benefits{
    gap: 0.75rem;
}
.challenge{
    gap: 0.4rem;
}
@media(min-width:640px){
    #welcome{
        padding: 1rem 0;
    }
}


</style>
