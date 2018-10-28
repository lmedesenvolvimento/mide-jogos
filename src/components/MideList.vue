<template>
  <v-container>
    <v-layout
      text-xs-center
      wrap
    >
        <v-flex s12>
          <v-card>
            <v-list two-line>
              <template v-for="(item, index) in this.mides">
                <v-list-tile
                  :key="index"
                  avatar
                >
                  <v-list-tile-avatar>
                    <img :src="item.screenshot_url">
                  </v-list-tile-avatar>

                  <v-list-tile-content>
                    <v-list-tile-title>{{item.name}}</v-list-tile-title>
                    <v-list-tile-sub-title>
                      <a :href="item.url" target="_blank">
                        {{item.url}}
                      </a>
                    </v-list-tile-sub-title>
                  </v-list-tile-content>
                </v-list-tile>
              </template>
            </v-list>
          </v-card>
        </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  import axios from 'axios'
  
  const api_key = '251f33159dbd96cbb5614f755ff8d982827e50ae42f5f88b1f97d480ba27be7a'

  export default {
    data(){
      return {
        mides: []
      }
    },
    async created(){
      let { data } = await axios.get(`https://api.netlify.com/api/v1/sites?access_token=${api_key}`);
      this.mides = data;
    }
  }
</script>
<style>

</style>
