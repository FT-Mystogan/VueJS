<template>
    <div>
        <h2>Manage Goals</h2>
        <input type="text" ref="goal">
        <button @click="setGoal">Set Goal</button>
        <teleport to='body'>
            <error-alert v-if="inputIsInvalid">
                <h2>Input is invalid!</h2>
                <p>Please enter at least a few characters...</p>
                <button @click="confirmError">Okay</button>
            </error-alert>
        </teleport>
    </div>
</template>

<script>
import ErrorAlertVue from './ErrorAlert.vue';
export default {
    component: {
        'error-alert': ErrorAlertVue,
    },
    data() {
        return {
            inputIsInvalid: false,
        }
    },
    methods: {
        setGoal() {
            const enterValue = this.$refs.goal.value;
            if (enterValue == '') {
                this.inputIsInvalid = true;
            }
        },
        confirmError() {
            this.inputIsInvalid = false;
        }
    },
}
</script>