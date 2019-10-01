<template>
  <v-layout>
    <v-flex>
      <div id="map-wrap" style="height: 100vh; width: 130vh">
 <no-ssr>
   <l-map :zoom=5 :center="[-29, 133.7751]">
     <l-tile-layer url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"></l-tile-layer>
     <l-circle-marker @mouseover="sydney()" @mouseleave="sydneyLeave()" :radius="3" :color="markerColour" :lat-lng="markers.sydney"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.canberra"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.newcastle"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.brokenHill"></l-circle-marker>
     <l-circle-marker @mouseover="melbourne()" @mouseleave="melbourneLeave()" :radius="5" :color="markerColour" :lat-lng="markers.melbourne"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.bendigo"></l-circle-marker>
     <l-circle-marker @mouseover="adelaide()" @mouseleave="adelaideLeave()" :radius="5" :color="markerColour" :lat-lng="markers.adelaide"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.aliceSprings"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.darwin"></l-circle-marker>
     <l-circle-marker @mouseover="perth()" @mouseleave="perthLeave()" :radius="5" :color="markerColour" :lat-lng="markers.perth"></l-circle-marker>
     <l-circle-marker @mouseover="albany()" @mouseleave="albanyLeave()" :radius="5" :color="markerColour" :lat-lng="markers.albany"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.kalgoorlie"></l-circle-marker>
     <l-circle-marker @mouseover="broome()" @mouseleave="broomeLeave()" :radius="5" :color="markerColour" :lat-lng="markers.broome"></l-circle-marker>
     <l-circle-marker @mouseover="launceston()" @mouseleave="launcestonLeave()" :radius="5" :color="markerColour" :lat-lng="markers.launceston"></l-circle-marker>
     <l-circle-marker @mouseover="hobart()" @mouseleave="hobartLeave()" :radius="5" :color="markerColour" :lat-lng="markers.hobart"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.mtIsa"></l-circle-marker>
     <l-circle-marker @mouseover="brisbane()" @mouseleave="brisbaneLeave()" :radius="5" :color="markerColour" :lat-lng="markers.brisbane"></l-circle-marker>
     <l-circle-marker @mouseover="rockhampton()" @mouseleave="rockhamptonLeave()" :radius="5" :color="markerColour" :lat-lng="markers.rockhampton"></l-circle-marker>
     <l-circle-marker  :radius="5" :color="markerColour" :lat-lng="markers.cairns"></l-circle-marker>
     <l-circle-marker @mouseover="mtAugusta()" @mouseleave="mtAugustaLeave()" :radius="5" :color="markerColour" :lat-lng="markers.ptAugusta"></l-circle-marker>

     <l-polyline :weight="3" :lat-lngs="polyline.sydMelb" :color="sydMelb"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.sydBris" :color="sydBris"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.sydCanb" :color="sydCanb"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.sydNew" :color="sydNew"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.sydBroke" :color="sydBroke"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.melbCanb" :color="melbCanb"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.melbAde" :color="melbAde"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.melbHob" :color="melbHob"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.melbBen" :color="melbBen"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.melbLaun" :color="melbLaun"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.adeBroke" :color="adeBroke"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.adePerth" :color="adePerth"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.adeDar" :color="adeDar"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.darAlice" :color="darAlice"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.perthAlb" :color="perthAlb"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.perthKal" :color="perthKal"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.perthBro" :color="perthBro"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.launHob" :color="launHob"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.brisMt" :color="brisMt"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.brisRock" :color="brisRock"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.brisCair" :color="brisCair"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.brisDar" :color="brisDar"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.mtDar" :color="mtDar"></l-polyline>
     <l-polyline :weight="3" :lat-lngs="polyline.adePt" :color="adePt"></l-polyline>

   </l-map>
 </no-ssr>
</div>
    </v-flex>
    <svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      markers: {
        sydney: [-33.8688, 151.2093],
        canberra: [-35.2809, 149.1300],
        newcastle: [-32.9283, 151.7817],
        brokenHill: [-31.9539, 141.4539],
        melbourne: [-37.8136, 144.9631],
        bendigo: [-36.7570, 144.2794],
        adelaide: [-34.9285, 138.6007],
        darwin: [-12.4634, 130.8456],
        aliceSprings: [-23.6980, 133.8807],
        perth: [-31.9505, 115.8605],
        albany: [-35.0269, 117.8837],
        kalgoorlie: [-30.7490, 121.4660],
        broome: [-17.9644, 122.2304],
        launceston: [-41.4332, 147.1441],
        hobart: [-42.8821, 147.3272],
        mtIsa: [-20.7256, 139.4927],
        brisbane: [-27.4698, 153.0251],
        rockhampton: [-23.3791, 150.5100],
        cairns: [-16.9186, 145.7781],
        ptAugusta: [-32.4952, 137.7894]
      },
      markerColour: '#D62839',
      classA: '#EF476F',
      classB: '#FFD166',
      classC: '#06D6A0',
      classD: '#118AB2',
      classE: '#073B4C',
      toDestination: 1,
      sydMelb: '#FFD166',
      sydBris: '#EF476F',
      sydCanb: '#FFD166',
      sydNew: '#EF476F',
      sydBroke: '#FFD166',
      melbCanb: '#FFD166',
      melbAde: '#EF476F',
      melbHob: '#EF476F',
      melbBen: '#EF476F',
      melbLaun: '#EF476F',
      adeBroke: '#06D6A0',
      adePerth: '#118AB2',
      adeDar: '#118AB2',
      darAlice: '#073B4C',
      perthAlb: '#06D6A0',
      perthKal: '#06D6A0',
      perthBro: '#06D6A0',
      launHob: '#FFD166',
      brisMt: '#EF476F',
      brisRock: '#EF476F',
      brisCair: '#EF476F',
      mtDar: '#FFD166',
      adePt: '#FFD166'
    };
  },
  computed: {
  polyline() {
    return {
    sydMelb: [this.markers.sydney, this.markers.melbourne],
    sydBris: [this.markers.sydney, this.markers.brisbane],
    sydCanb: [this.markers.sydney, this.markers.canberra],
    sydNew: [this.markers.sydney, this.markers.newcastle],
    sydBroke: [this.markers.sydney, this.markers.brokenHill],
    melbCanb: [this.markers.melbourne, this.markers.canberra],
    melbAde: [this.markers.melbourne, this.markers.adelaide],
    melbHob: [this.markers.melbourne, this.markers.hobart],
    melbBen: [this.markers.melbourne, this.markers.bendigo],
    melbLaun: [this.markers.melbourne, this.markers.launceston],
    adeBroke: [this.markers.adelaide, this.markers.brokenHill],
    adePerth: [this.markers.adelaide, this.markers.perth],
    adeDar: [this.markers.adelaide, this.markers.darwin],
    darAlice: [this.markers.darwin, this.markers.aliceSprings],
    perthAlb: [this.markers.perth, this.markers.albany],
    perthKal: [this.markers.perth, this.markers.kalgoorlie],
    perthBro: [this.markers.perth, this.markers.broome],
    launHob: [this.markers.launceston, this.markers.hobart],
    brisMt: [this.markers.brisbane, this.markers.mtIsa],
    brisRock: [this.markers.brisbane, this.markers.rockhampton],
    brisCair: [this.markers.brisbane, this.markers.cairns],
    mtDar: [this.markers.mtIsa, this.markers.darwin],
    adePt: [this.markers.adelaide, this.markers.ptAugusta],
    }
  }
  },
  methods: {
    sydney() {
      this.sydMelb = this.classC
      this.sydBris = this.classB
      this.sydCanb = this.classB
    },
    sydneyLeave() {
      this.sydMelb = this.classB
      this.sydBris = this.classA
    },
     melbourne() {
       this.melbAde = this.classC
       this.melbLaun = this.classB
     },
     melbourneLeave() {
       this.melbAde = this.classA
       this.melbLaun = this.classA
     },
     adelaide() {
       this.adePerth = this.classC
       this.adePt = this.classC
     },
     adelaideLeave() {
       this.adePerth = this.classD
       this.adePt = this.classB
     },
     perth() {
       this.adePerth = this.classC
       this.perthAlb = this.classB
       this.perthBro = this.classB
     },
     perthLeave() {
       this.adePerth = this.classD
       this.perthAlb = this.classC
       this.perthBro = this.classC
     },
     albany() {
       this.perthAlb = this.classB
     },
     albanyLeave() {
       this.perthAlb = this.classC
     },
     broome() {
       this.perthBro = this.classB
     },
     broomeLeave() {
       this.perthBro = this.classC
     },
     launceston() {
       this.launHob = this.classA
       this.melbLaun = this.classB
     },
     launcestonLeave() {
       this.launHob = this.classB
       this.melbLaun = this.classA
     },
     hobart() {
       this.launHob = this.classA
     },
     hobartLeave() {
       this.launHob = this.classB
     },
     brisbane() {
       this.brisRock = this.classB
     },
     brisbaneLeave() {
       this.brisRock = this.classA
     },
     rockhampton() {
       this.brisRock = this.classB
     },
     rockhamptonLeave() {
       this.brisRock = this.classA
     },
     mtAugusta() {
       this.adePt = this.classC
     },
     mtAugustaLeave() {
       this.adePt = this.classB
     }
  }
}
</script>


