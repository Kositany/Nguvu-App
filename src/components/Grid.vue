<script setup>
import {workoutProgram} from '../utils'

defineProps({
    handleSelectWorkout: Function,
    firstIncompleteWorkoutIndex: Number,
    handleResetPlan: Function
})

const workoutTypes =['Push','Pull','Legs']
</script>

<template>
<section id="grid">
    <button :disabled="workoutIdx > 0 && workoutIdx > firstIncompleteWorkoutIndex " @click="()=>handleSelectWorkout(workoutIdx)" :key="workoutIdx" v-for="(workout, workoutIdx) in Object.keys(workoutProgram)" class="card-button plan-card">
        <div>
            <p>Day {{workoutIdx<9 ? '0'+(workoutIdx +1) : workoutIdx +1 }}</p>
            <i class="fas fa-dumbbell" v-if="workoutIdx % 3 === 0"></i>
            <i class="fas fa-weight-hanging" v-if="workoutIdx %3 === 1"></i>
            <i class="fas fa-bolt" v-if="workoutIdx %3 === 2"></i>
        </div>
        <h3>{{ workoutTypes[workoutIdx % 3] }}</h3>
    </button>
    <button :disabled="firstIncompleteWorkoutIndex !=-1" @click="handleResetPlan" class="card-button plan-card-reset">
        <p>Reset <i class="fas fa-rotate-left"></i></p>
    </button>
</section>
</template>

<style scoped>
#grid{
    display: grid;
    grid-template-columns: repeat(3, minmax(0,1fr));
    gap: 1rem;
}
#grid button{
    width: 100%;
}
#grid button:disabled{
    box-shadow: none;
}
.plan-card{
    display: flex;
    flex-direction: column;
}
.plan-card-reset{
    align-items: center;
    justify-content: center;
    gap: 1rem;
    display: flex;
}
.plan-card div{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap:1rem;
}

@media (min-width:640px) {
    #grid{
        grid-template-columns: repeat(4, minmax(0,1fr));
    }
}
@media (max-width:500px) {
    #grid{
        grid-template-columns: repeat(2, minmax(0,1fr));
    }
}
@media (max-width:420px) {
    #grid{
        grid-template-columns: repeat(1, minmax(0,1fr));
    }
}


</style>
