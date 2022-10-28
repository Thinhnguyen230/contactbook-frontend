<script>
export default {
    prop: {
        moduleValue: {  type: String, default: ''},
    },
    emits: ['submit', 'update:moduleValue'],
    methods: {
        updateModelValue(e) {
            this.$emit('update:moduleValue', e.target.value);
        },
        submit() {
            this.$emit('submit');
        },
    },
};
</script>
<template>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="Nhập thông tin cần tìm" :value="modelValue"
            @input="updateModelValue" @keyup.enter="submit">
        <div class="input-group-append">
            <button class="btn btn-outline-secondary" type="button" @click="submit">
                <i class="fas fa-search" /> Tìm kiếm
            </button>
        </div>
    </div>
</template>