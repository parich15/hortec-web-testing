<template>
  <div class="TarjetaIcono">
    <div v-for="(item,idx) in items" :key="idx" class="BodyTjt d-flex flex-row mx-auto" data-aos="fade-in" data-aos-delay="300">
      <div class="icono mr-4 ml-3">
        <b-icon :icon="item.icono" />
      </div>
      <div class="info my-3">
        <h4>{{ item.titulo }}</h4>
        <p>{{ item.desc }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TarjetasIcono',
  data () {
    return {
      items: [
        {
          icono: 'telephone',
          titulo: this.$i18n.t('Contacto.telf'),
          desc: '(+34) 606 90 33 10'
        },
        {
          icono: 'envelope',
          titulo: this.$i18n.t('Contacto.mail'),
          desc: 'info@hortec.org'
        },
        {
          icono: 'signpost-split',
          titulo: this.$i18n.t('Contacto.loc'),
          desc: 'Carrer Transversal 2, 53, 08040'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
