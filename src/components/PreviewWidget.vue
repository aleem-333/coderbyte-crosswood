<template>
    <div class="preview">
        <div class="card bg-dark p-3">
          <!-- Card header START -->
          <div class="card-header border-0 pb-0 text-white">
            Preview
          </div>

          <div class="card-body">
            <div class="row">
              <div class="col-md-12">
                <div class="card bg-dark p-3">
                  <div class="card-body">
                    <div class="row">
                      <div class="col-md-12">
                        <h3 class="text-light">{{ form.question }}</h3>
                      </div>
                    </div>
                    <div class="row">
                      <div class="col-md-12">
                        <ul class="list-group">
                          <li v-for="(option, index) in form.options" :key="index" class="list-group-item bg-dark-500 border-dark text-light">
                            <label>
                              <input type="radio" name="correctAnswer" :checked="(index == form.correctAnswer) ? true : false" />
                              {{ option }}
                            </label>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PreviewWidget',
    props: ['form'],
    mounted() {
        console.log(this.form);
    }
}
</script>