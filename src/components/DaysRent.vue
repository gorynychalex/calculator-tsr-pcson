<template>
    <div class="container">
        <b-form-group
                id="input-days-rent-label"
                label="Планируемое количество суток для проката:"
                label-for="input-days-rent"
                description="На сколько дней планируется арендовать средство для проката."
        >
            <b-form-input
                    id="input-days-rent"
                    v-model="days"
                    type="number"
                    min="0" max="1000" step="1"
                    required
                    placeholder="0"
                    @change="$emit('newDays',days)"
            ></b-form-input>
        </b-form-group>
    </div>
</template>

<script>
    export default {
        name: "DaysRent",
        data(){
            return {
                days: 0
            }
        },
    }
</script>

<style scoped>

</style>