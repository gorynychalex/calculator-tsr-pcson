<template>
    <div class="container">
        <b-form-group label="Льготы, скидка 50%:">
            <b-form-radio v-for="privilege in privileges" :key="privilege.id" v-model="selected" name="privilege" :value="privilege.id" @input="$emit('pickedOpt',selected)" >
                {{ privilege.title }}
            </b-form-radio>
        </b-form-group>
        <!--<div class="mt-3">Selected: <strong>{{ selected }}</strong></div>-->
    </div>
</template>

<script>

    export default {
        name: "Privileges",
        props: {
            privileges: Array
        },
        data: function(){
            return {
                selected: 0
            }
        },
    }
</script>

<style scoped>

</style>