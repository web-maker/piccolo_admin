<template>
    <select :name="columnName + '__operator'">
        <option
            :key="operator.label"
            :selected="operator.value == 'e'"
            :value="operator.value"
            v-for="operator in operators"
        >
            {{ operator.label }}
        </option>
    </select>
</template>

<script lang="ts">
import Vue, {PropType} from "vue"

export default Vue.extend({
    props: {
        columnName: {
            type: String as PropType<string>,
            required: true
        }
    },
    data() {
        return {
            operators: [
                {
                    label: "Equals",
                    value: "e"
                },
                {
                    label: "Less Than",
                    value: "lt"
                },
                {
                    label: "Less Than or Equal To",
                    value: "lte"
                },
                {
                    label: "Greater Than or Equal To",
                    value: "gte"
                },
                {
                    label: "Greater Than",
                    value: "gt"
                }
            ]
        }
    }
})
</script>

<style></style>
