<template>
  <div class="card shadow mb-0 w-75">
    <div class="card-body px-5">
      <div class="row d-flex justify-content-between">
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
        },
        {
          title: 'DTI CALCULATOR',
          url: 'https://tendo-dti-calculator.netlify.app/'
        },
        {
          title: 'ELS FORMATTER',
          url: 'https://tendo-els-formatter.netlify.app/'
        },
        {
          title: 'LOAN FORMATTER',
          url: 'https://tendo-loan-formatter.netlify.app/'
        },
        {
          title: 'LOAN CALCULATOR',
          url: 'https://tendo-loan-calculator.netlify.app/'
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
    height: 150px;
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

  .tool-3 {
    background: linear-gradient(135deg, #FF9E05, #FFF8B4);
  }

  .tool-4 {
    background: linear-gradient(135deg, #E63E4C, #D5ACC1);
  }

  .tool-5 {
    background: linear-gradient(135deg, #69CEEE, #EFB9E5);
  }

  .tool-6 {
    background: linear-gradient(135deg, #EDDCE2, #99A8C3);
  }
</style>
