<template>
   <div class="wrapper">
      <v-layout align-center grid-list-md row wrap>
         <v-flex xs12 sm6 offset-sm3>
            <v-card>
               <v-tabs centered color="orange lighten-1" dark icons-and-text >
               <v-tabs-slider color="indigo accent-4">
               </v-tabs-slider>
                  <v-tab href="#tab-1">
                     Sign up
                  </v-tab>

                  <v-tab href="#tab-2">
                     Login
                  </v-tab>

                  <v-tab-item v-for="i in 2" :key="i" :value="'tab-' + i" >
                     <v-card flat>
                           <v-card>
                              <v-img
                                 class="white--text"
                                 height="200px"
                                 src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                              >
                                 <v-container fill-height fluid>
                                    <v-layout fill-height>
                                    <v-flex xs12 align-end flexbox>
                                       <span class="headline">Top 10 Australian beaches</span>
                                    </v-flex>
                                    </v-layout>
                                 </v-container>
                              </v-img>
                              
                              <v-card-text>
                                 {{ text }}
                                 <v-form>
                                    <v-text-field prepend-icon="person" name="login" label="Login" type="text"></v-text-field>
                                    <v-text-field prepend-icon="lock" name="password" label="Password" id="password" type="password"></v-text-field>
                                 </v-form>
                              </v-card-text>
                              <v-card-actions>
                                 <v-spacer></v-spacer>
                                 <v-btn color="indigo darken-4" dark>Login</v-btn>
                              </v-card-actions>
                           </v-card>
                     </v-card>
                  </v-tab-item>

               </v-tabs>
            </v-card>
         </v-flex>
      </v-layout>

      <v-footer dark height="auto">
         <v-card
            color="blue-grey lighten-2"
            flat
            tile
         >
            <v-card-title>
            <strong class="subheading">Get connected with us on social networks!</strong>

            <v-spacer></v-spacer>

            <v-btn
               v-for="icon in icons"
               :key="icon"
               class="mx-3"
               dark
               icon
            >
               <v-icon size="24px">{{ icon }}</v-icon>
            </v-btn>
            </v-card-title>

            <v-card-actions class="blue-grey darken-3 justify-center">
            &copy;2018 — <strong>YSK DESIGN</strong>
            </v-card-actions>
         </v-card>
      </v-footer>

   </div>
</template>

<script>
import firebase from '~/utillis/firebase';
import Vue from 'vue';
import Vuetify from 'vuetify';
import '@fortawesome/fontawesome-free/css/all.css'

export default {
   components: {

   },
   props: {
      hoge: {
         type: Array,
         default: () => [],
         source: String
      }
   },
   data() {
      return {
      text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      icons: [
         'fab fa-facebook',
         'fab fa-twitter',
         'fab fa-google-plus',
         'fab fa-linkedin',
         'fab fa-instagram'
      ],
      drawer: null
      };
   },

   computed: {
      
   },
   methods: {

   }
}
</script>


<style scoped>
.label {
   margin-bottom: 50px;
}

.app {
   display: flex;
   flex-direction: column;

}

body,
.wrapper {
   display: flex;
   flex-direction: column;
   min-height: 100vh;
   align-items: center;
   font-family: 'Yu Gothic','Hiragino Kaku Gothic ProN','ヒラギノ角ゴ ProN W3','ヒラギノ角ゴシック','Hiragino Sans';;
   background-image: url(DSC03528.JPG);    /* 背景画像指定 */
   background-size:  cover;                /* 画像のサイズ指定 */
}

footer {
   margin-top: auto;
}
</style>