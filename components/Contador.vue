<template>
  <div class="contador d-flex">
    <h4>{{ contador }}</h4>
    <h6>{{ titulo }}</h6>
  </div>
</template>

<script>
// import anime from 'animejs/lib/anime.es.js'

export default {
  name: 'Contador',
  props: {
    numero: {
      type: Number,
      default: 0
    },
    titulo: {
      type: String,
      default: 'Texto Contador'
    }
  },
  data () {
    return {
      contador: 0,
      num: this.numero
    }
  },
  watch: {
    num (val) {
      this.setContador(val)
    }
  },
  mounted () {
    // Activar Contador cuando esté en el viewport
    // NO TOCAR
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.intersectionRatio >= 0.7) {
            this.setContador(this.num)
            observer.disconnect()
          }
        })
      },
      {
        threshold: 0.7
      }
    )
    observer.observe(document.querySelector('.contador'))
  },
  methods: {
    setContador (val) {
      const obj = { n: this.contador }
      this.$anime({
        targets: obj,
        n: val,
        round: 1,
        duration: 1500,
        easing: 'linear',
        update: () => {
          this.contador = obj.n
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
