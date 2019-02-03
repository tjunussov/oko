<template lang="pug">
doctype html
b-card-group.uyi.devices(deck)
  template(v-for="(c,z) in companies")
    h6.w100 {{c.title}}
    .complex(v-for="(v,k,j) in c.items")
      h1.mb-0 {{k}}
      .binfo.branch.branch-mini.small(v-for="i in v" v-b-modal.inner) 
        h2.mb-0 Ω БЛОК {{(i)}}
        v 10 /
        ds(v-if="i+j+z == r")/
        v 5
        br/
        v 5
        br/
        v(:class="{max:(i+j+z == r)}") 5
  b-modal#inner(no-fade hide-header size="lg")
    img(src="/static/hud/EngineeringUI_V2526.png")

</template>

<script>

import Vue from 'vue'


Vue.config.ignoredElements = ['v']

export default {
  name: 'List',
  data(){
    return {
      r:5,
      companies:[
{"title":"Астана ЖилСервис НС",items:{
"ЖК Park Avenue Exclusive":3,
"ЖК Ray Residence":3,
"ЖК Bi City Tokyo":8,
"ЖК Alan":1,
"ЖК Akbulak Life":3,
"ЖК Мәңгілік":3,
"ЖК Crocus City":3,
"ЖК Dream City":3,
"ЖК Panorama Park":3,
"ЖК Avenue 5":3,
"ЖК Nura EsiL":5,
"ЖК Light House":3,
"ЖК Orynbor Towеrs":3,
"ЖК Зеленый квартал":3,
"ЖК BI City Seoul":6,
"ЖК 7Я":3,
"ЖК Времена года":3,
"ЖК Арнау":6,
"ЖК Берекет":1,
"ЖК Ботанический":1,
"ЖК Expo Residence":3,
"ЖК Esil Riverside":3,
"ЖК Green Park":1,
"ЖК Vivat Promenade":1,
"ЖК Sauran Towers":2,
"ЖК Promenade Expo":3,
// },{"title":"Астана ЖилСервис",items:{
  "ЖК Park Avenue":3,
"ЖК Камал":3,
"ЖК Премьера":3,
"ЖК Парижский квартал":3,
"ЖК Созвездие":3,
"ЖК Gagarin Park":3,
"ЖК Миланский квартал":3,
"ЖК Лазурный Квартал":3,
"ЖК Кайнар":3,
"ЖК Саламат":3,
"ЖК Сезам":3,
"ЖК ART House":3,
"ЖК Expo Boulevard":3,
"ЖК Family Town":3,
"ЖК Comfort Town":3,
"ЖК Триумфальная Арка":3,
"ЖК Deluxe Town":3,
"ЖК BI Town":7,
"ЖК Верный":3,
"ЖК Жигер 2":3}
},{"title":"Village Service",items:{
"КГ Garden Village":3,
"КГ Family Village":3,
"КГ BI Village":3,
"КГ Vela Village":3}
},{"title":"Luxury Concierege Astana",items:{
"ЖК Британский квартал":3,
"ЖК Akbulak Town":3,
"ЖК Viva Plaza":3,
"ЖК Отау":3,
"ЖК Жигер":3,
"ЖК Шахар":3,
"ЖК Арабика":3,
"ЖК Арман Кала":3,
"ЖК Гульдер":3,
"ЖК Аврора":3,
"ЖК Апато":3,
"ЖК Восточный":3,
"ЖК Дуэт":3,
"ЖК Соло":3,
"ЖК Факультет":3,
"ЖК Социал":3,
"ЖК Апато Тауэр":3,
"ЖК Восточный 2":3,
"ЖК Этюд":3}
},{"title":"BIG House",items: {
"ЖК Шанырак":3,
"ЖК Шанырак Премиум":3,
"ЖК Солнечный":3,
"ЖК Солнечный Город":3,
"ЖК Симфония":3,
"ЖК Сармат":3,
"ЖК Номад":3,
"ЖК Мирас":3,
"ЖК Мереке":3,
"ЖК Мереке 2":3,
"ЖК Кулагер":3,
"ЖК Краун Плаза":3,
"ЖК Зерде":3,
"ЖК Достар 1":3,
"ЖК Болашак":3,
"ЖК Байконыс":3,
"ЖК NovaCity":10}
}
      ],
    }
  },
  computed:{
  },
  mounted(){
    window.setInterval(()=>{ this.r = Math.floor(Math.random()*50) },5000)
  },
  methods:{
    enter(el){
      var newVal = el.parentElement.dataset.newvalue;
      var oldVal = el.parentElement.dataset.value
          el.parentElement.dataset.value = newVal
      if(newVal!=0&&newVal!=1){
          if(oldVal != null) {
            if(newVal > oldVal) el.parentElement.dataset.dir = 'up'
            else if(newVal < oldVal) el.parentElement.dataset.dir = 'down'
            else el.parentElement.dataset.dir = ''
          }
      }
    },
    leave(el){
      el.parentElement.dataset.dir = ''
    },
  }
}


</script>

<style lang="stylus">
</style>