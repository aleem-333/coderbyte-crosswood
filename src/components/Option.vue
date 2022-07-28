<template>
    <div class="row w-100 mb-2 m-auto">
        <div class="col">
            <b-form-input
                v-model="name"
                :value="name"
                @keyup="$emit('update-option-name', name, index)"
                placeholder="Enter your multiple choice option"
                class="bg-dark-500 border-dark text-light"
            ></b-form-input>
        </div>
        <div class="col-md-2 px-2 text-right">
            <b-form-radio
                    value="correct"
                    name="correct"
                    v-model="correct"
                    class="bg-dark-500 border-dark d-inline text-light"
                    @change="$emit('update-correct-answer', index)"
                ></b-form-radio>
            <b-button type="button" variant="success" class="ms-2" v-if="action == 'add' || action == 'both'" @click="$emit('add-row')">+</b-button>
            <b-button type="button" variant="danger" class="ms-2" v-if="action == 'remove' || action == 'both'" @click="$emit('remove-row', index)">-</b-button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AnswerOption',
    data() {
        return {
            name: '',
            correct: false
        };
    },
    props: [
        'text',
        'index',
        'action'
    ],
    computed: {
        optionName() {
            return this.text;
        },
        
    },
    methods: {
        addRow() {
            console.log('add row option', this);
            this.$parent.addOptionRow;
        },
    },
    mounted() {
        this.name = this.text;
    },
}
</script>