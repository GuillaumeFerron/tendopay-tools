<template>
  <div class="card shadow mb-0 w-75">
    <div class="card-body px-5">
      <div class="row">
        <div class="card col-3 m-3 tool mh-2 d-flex justify-content-center align-items-center clickable"
          v-for="(tool, key) in tools" v-bind:key="tool.title" @mouseenter="onHover(key, true)" @mouseleave="onHover(key, false)"
          :class="(hover[key] ? 'shadow' : '') + ' tool-' + key"
          @click="goToTool(tool)">
          <div>
            <h4 class="text-white"><b>{{ tool.title }}</b></h4>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      hover: { },
      tools: [
        {
          title: 'INCOME CALCULATOR',
          url: 'https://tendo-income-calculator.netlify.app/'
        },
        {
          title: 'IR CORRECTOR',
          url: 'https://tendo-ir-corrector.netlify.app/'
        },
        {
          title: 'DTI ADJUSTER',
          url: 'https://tendo-dti-adjuster.netlify.app/'
        }
      ]
    }
  },
  methods: {
    onHover(key, enter) {
      this.hover[key] = enter
    },
    goToTool(tool) {
      window.open(tool.url, '_blank');
    }
  }
}
</script>

<style lang="scss" scoped>
 .shadow {
    -webkit-box-shadow: 5px 5px 15px 5px rgba(0, 0, 0, 0.3);
    box-shadow: 5px 5px 15px 5px rgba(0, 0, 0, 0.3);
  }

  .tool {
    height: 100px;
    transition: all 0.2s ease;
  }

  .tool-0 {
    background: linear-gradient(135deg, #0a2da2, #b11bbb);
  }

  .tool-1 {
    background: linear-gradient(135deg, #b1f5bc, #024bcf);
  }

  .tool-2 {
    background: linear-gradient(135deg, #F62881, #00B665);
  }
</style>
