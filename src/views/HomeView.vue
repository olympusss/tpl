<template>
  <v-app 
    id="inspire" 
    :style="{background: $vuetify.theme.themes.dark.background}"
    style="font-family: 'SF UI Display';"
  >
    <ToolBar />
    <v-container>
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
            class="mt-n2"
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
            <router-link 
              to="/" 
              tag="span" 
              class="pointer"
            >
              Halanlarym
            </router-link>
          </v-toolbar-title>

          <v-toolbar-title
            style="align-self: center;"
            class="mx-4"
          >
            <router-link 
              to="/" 
              tag="span" 
              class="pointer"
            >
              Meniň bilidirişlerim
            </router-link>
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
          <v-icon 
            size="30" 
            color="#212135"
          >
            location_on
          </v-icon>
        </v-btn>

        <v-btn 
          icon
          tile
          flat
          style="background-color: white;"
          class="py-0 mr-n4"
          height="40"
          width="40"
        >
          <v-icon 
            size="30" 
            color="#212135"
          >
            perm_identity
          </v-icon>
        </v-btn>

      </v-app-bar>
      <SearchComponent />
      
      <v-carousel 
        hide-delimiters 
        height="400"
        next-icon="mdi-arrow-right"
        prev-icon="mdi-arrow-left"
        style="margin: 20px 0; border-radius: 5px;"
      >
        <template v-slot:prev="{ on, attrs }">
          <v-btn
            class="carousel-btn"
            v-bind="attrs"
            v-on="on"
            height="40"
            width="40"
          >
            <v-icon size="40">chevron_left</v-icon>
          </v-btn>
        </template>
        <template v-slot:next="{ on, attrs }">
          <v-btn
            class="carousel-btn"
            v-bind="attrs"
            v-on="on"
            height="40"
            width="40"
          >
            <v-icon size="40" width="40" height="40">chevron_right</v-icon>
          </v-btn>
        </template>
        <v-carousel-item
          v-for="(item,i) in items"
          :key="i"
          :src="item.src"
        ></v-carousel-item>
      </v-carousel>

      <v-banner
        color="accent"
        rounded
        height="120"
      >
      </v-banner>
    </v-container>
    <FooterComponent />
  </v-app>
</template>

<script>
  import ToolBar from '../components/main/ToolBar'
  import FooterComponent from '../components/main/FooterComponent'
  import SearchComponent from '../components/main/SearchComponent'

  export default {
    data: () => ({
      toolbars: [
        { title: 'Bölümler' },
        { title: 'Halanlarym' },
        { title: 'Meniň bilidirişlerim' },
      ],
      items: [
          {
            src: 'https://analyzemedia.files.wordpress.com/2013/10/m_pepsi_versiontypo_fullldef_0636.jpg?w=1200&h=800&crop=1',
          },
          {
            src: 'https://www.audi.com/content/dam/ci/Guides/Communication_Media/Advertisements/02_Andwendungsbeispiele/audi-ci-communication-media-advertisements-example1.png?imwidth=2400',
          },
          {
            src: 'https://i0.wp.com/www.msureporter.com/wp-content/uploads/2017/04/SpriteWEB.jpg?fit=720%2C415&ssl=1',
          },
          {
            src: 'https://images.squarespace-cdn.com/content/v1/5aa96c579772aea9adaa2ef7/1591278959132-H8Q2M1GRA0NZKSS8SNGS/HealthAdvertisements_620.jpg',
          },
        ],
    }),
    components: {
      ToolBar,
      FooterComponent,
      SearchComponent
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

.carousel-btn {
  width: 40px;
  height: 40px;
  background-color: red;
}
</style>
