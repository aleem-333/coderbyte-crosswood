<template>
    <div class="h-100">
        <b-card class="bg-dark  text-start">
            <b-card-header class="text-light">
                Add Questions
            </b-card-header>
            <b-card-body class="text-start">
                <b-form @submit="onSubmit" @reset="onReset" v-if="show" class="bg-dark p-3">
                    <b-form-group
                        label="Question"
                        label-for="textarea-formatter"
                        class="mb-2 text-muted text-start"
                        >
                        <b-form-textarea
                            id="textarea-formatter"
                            v-model="form.question"
                            placeholder="Enter your text"
                            :formatter="formatter"
                            class=" bg-dark-500 border-dark text-light"
                        ></b-form-textarea>
                    </b-form-group>
                    <b-form-group
                        label="Answers"
                        label-for="textarea-formatter"
                        class="mb-2 text-muted text-right"
                        >
                        <Option 
                            v-for="(option, index) in form.options"
                            :key="index"
                            :action="(index + 1 == form.options.length) ? 'both' : 'remove'"
                            :index="index"
                            :text="option"
                            @add-row="addOptionRow"
                            @remove-row="removeOptionRow"
                            @update-option-name="updateOptionName"
                        >
                        </Option>
                    </b-form-group>
        
                    <b-button type="submit" variant="primary">Submit</b-button>
                    <b-button type="reset" variant="danger">Reset</b-button>
                </b-form>
            </b-card-body>
        </b-card>
    </div>
</template>
<script>
import Option from './Option.vue'
export default {
    name: "FormWidget",
    data() {
        return {
            form: {
                question: "",
                options: ['abc', 'def', 'ghi'],
                correctAnswer: ""
            },
            show: true
        };
    },
    methods: {
        onSubmit(event) {
            event.preventDefault();
            alert(JSON.stringify(this.form));
        },
        onReset(event) {
            event.preventDefault();
            // Reset our form values
            this.form.question = "";
            this.form.options = "";
            this.show = false;
            this.$nextTick(() => {
                this.show = true;
            });
        },
        updateOptionName(option, index) {
            this.form.options[index] = option;
        },
        addOptionRow() {
            console.log('add row form');
            this.form.options.push("");
        },
        removeOptionRow(index) {
            this.form.options.splice(index, 1);
        }
    },
    components: { Option }
}
</script>