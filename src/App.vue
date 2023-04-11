
<template>
  <a-layout>
    <a-layout-header>
        <a-typography-title :style="{color: 'white',display: 'flex',alignItems :'center',height:'100%'}">
        Web3 Links
        </a-typography-title>
    </a-layout-header>

    <a-layout-content>
      <div :style="{ background: '#fff',minHeight: '900px',padding:'50px'}">

        <a-list :grid="{ gutter: 16, column: 1}" :data-source="data">
          <template #renderItem="{ item }">
            <a-list-item>
              <h3 :style="{ marginBottom: '16px' }">{{item.title}}</h3>

                <a-list :grid="{ gutter: 16, column: 3}" :data-source="item.data">

                  <template #renderItem="{item:item2}">
                    <a-list-item>

                      <a-card hoverable>
                        <template #actions>
                          <a :href="item2.homepage" target="_blank" title="Home Page" > <svg class="fusion small"><use xlink:href="@/assets/fusion-interface.svg#home"></use></svg></a>
                          <a :href="item2.wallet" target="_blank" title="Wallet" > <svg class="fusion small"><use xlink:href="@/assets/fusion-web3.svg#dcentwallet"></use></svg></a>
                          <a :href="item2.whitePaper" target="_blank" title="White Paper" > <svg class="fusion small"><use xlink:href="@/assets/fusion-interface.svg#file_pdf"></use></svg></a>
                          <a :href="item2.socialMedia" target="_blank" title="Social Media" ><svg class="fusion small"><use xlink:href="@/assets/fusion-interface.svg#phone_video_pc"></use></svg></a>
                        </template>

                        <a-card-meta :title="`${item2.name}&nbsp;(${item2.symbol})`" :description="item2.description">
                          <template #avatar>
                            <svg class="fusion small"> <use :xlink:href="'/src/assets/fusion-coins.svg#'+ item2.icon"></use></svg>
                          </template>
                        </a-card-meta>
                      </a-card>

                    </a-list-item>
                  </template>
                </a-list>



            </a-list-item>
          </template>
        </a-list>
      </div>
    </a-layout-content>

    <a-layout-footer>Footer</a-layout-footer>
  </a-layout>
</template>


<script lang="ts">
import mainData from './assets/main.json'



export default {
  data() {
    return {
      data: mainData
    }
  },

}


</script>

<style scoped>
.fusion{
  background-color: white;
  stroke: black;
  stroke-width: 2px;
  stroke-miterlimit: 5;
  width: 64px;
  height: 64px;
  fill: none;
}
.fusion.small{
  width: 32px;
  height: 32px;
}
</style>
