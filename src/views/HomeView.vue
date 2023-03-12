<template>
  <v-app 
    id="inspire" 
    :style="{background: $vuetify.theme.themes.dark.background}"
  >
    <ToolBar />
    <v-container 
      class="pa-0 mt-2" 
      height="60" 
      style="background-color: red;"
    >
      <v-app-bar
        dense
        flat
        height="60"
        color="#EEEEEE"
      >
        <v-toolbar-title>
          <div>
            <b 
              class="mytitle"
            >
              TELEKEÇI
            </b>
          </div> 
          <div 
            class="mt-n3"
          >
            <b 
              class="mytitle"
            >
              PLATFORMA
            </b>
          </div>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        
        
        <v-toolbar-items>
          <v-toolbar-title
            style="align-self: center;"
            class="mx-4"
          >
            <router-link 
              to="/" 
              tag="span" 
              class="pointer"
            >
              Bölümler
              <v-icon 
                class="ml-n1"
              >
                keyboard_arrow_down
              </v-icon>
            </router-link>
          </v-toolbar-title>

          <v-toolbar-title
            style="align-self: center;"
            class="mx-4"
          >
            <router-link to="/" tag="span" class="pointer">Halanlarym</router-link>
          </v-toolbar-title>

          <v-toolbar-title
            style="align-self: center;"
            class="mx-4"
          >
            <router-link to="/" tag="span" class="pointer">Meniň bilidirişlerim</router-link>
          </v-toolbar-title>
        </v-toolbar-items>


        <v-btn 
          icon
          tile
          flat
          style="background-color: white;"
          class="py-0 mx-5"
          height="40"
          width="40"
        >
          <v-icon size="30" color="#212135">location_on</v-icon>
        </v-btn>

        <v-btn 
          icon
          tile
          flat
          style="background-color: white;"
          class="py-0 mr-0"
          height="40"
          width="40"
        >
          <v-icon size="30" color="#212135">perm_identity</v-icon>
        </v-btn>

      </v-app-bar>
    </v-container>
    <FooterComponent />
  </v-app>
</template>

<script>
  import ToolBar from '../components/ToolBar'
  import FooterComponent from '../components/FooterComponent'

  export default {
    data: () => ({
      toolbars: [
        { title: 'Bölümler' },
        { title: 'Halanlarym' },
        { title: 'Meniň bilidirişlerim' },
      ]
    }),
    components: {
      ToolBar,
      FooterComponent
    },
  }
</script>

<style>
.mytitle {
  font-size: 20px !important;
  font-weight: 800;
  color: #212135;
}

.pointer {
  cursor: pointer;
  font-size: medium;
  font-weight: 700;
  color: #212135;
}
</style>
