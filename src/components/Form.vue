<script setup>

const props = defineProps(['setValuea', 'setOperator', 'setValueb'])
</script>
<template>
    <div class="container">
        <div class="row">
            <div class="col">
                <input type="number" class="form-control" placeholder="First value" aria-label="First value" @keyup="props.setValuea
                " >
            </div>
            <div class="col">
                <select name="operation" class="form-select" @change="props.setOperator">
                    <option value="sum" selected>+</option>
                    <option value="subs">-</option>
                    <option value="mult">*</option>
                    <option value="div">/</option>
                </select>
            </div>
            <div class="col">
                <input type="number" class="form-control" placeholder="Last value" aria-label="Last value" @keyup="props.setValueb">
            </div>
        </div>
    </div>
</template>