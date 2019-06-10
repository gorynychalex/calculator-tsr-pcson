<template>
    <div class="container">
        <b-form-group id="equipments" label="Средства реабилитации:" label-for="reabilitaionEquipment">

            <b-form-select id="reabilitaionEquipment"
                           v-model="selected"
                           @change="$emit('equipmentSelect', selected)"
                           :options="equipmentList"
                           text-field="name" value-field="id"
                           required
            >

            </b-form-select>
            <div class="mt-3">Цена: <strong>{{ selected ? equipments[selected].price : null }}</strong> руб.</div>
        </b-form-group>
    </div>
</template>

<script>


    export default {
        name: "Equipment",
        props: {
            equipments: Array
        },
        data() {
            return {
                equipmentList: [ {"id": null, "name": "Выберите средство ...", "price": null}, ...this.equipments],
                selected: null
            }
        }
    }
</script>

<style scoped>

</style>