<template>
    <div class="container">
        <b-form-group id="equipments" label="Средства реабилитации:" label-for="reabilitaionEquipment">

            <b-form-select id="reabilitaionEquipment" v-model="selected" :options="equipmentList" text-field="name" value-field="price" required></b-form-select>

            <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>

        </b-form-group>
    </div>
</template>

<script>
    import equipments from '@/data/tsr-equipment.json'

    export default {
        name: "Equipment",
        props: {

        },
        data() {
            return {
                equipments,
                equipmentList: [ {"id": null, "name": "Выберите средство ...", "price": null}, ...equipments],
                selected: null
            }
        }
    }
</script>

<style scoped>

</style>