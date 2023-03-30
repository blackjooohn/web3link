<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

</script>

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

                  <template #renderItem="{item2}">
                    <a-list-item>
                      <template #actions>
<!--                        <component :is="" style="margin-right: 8px" />-->
                        <svg class="fusion small">
                          <use xlink:href="@/assets/fusion-coins.svg#ONEINCH_8104"></use>
                        </svg>
                      </template>

                      <a-card :title="item2.name">
                        {{item2.description}}

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
  }
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
