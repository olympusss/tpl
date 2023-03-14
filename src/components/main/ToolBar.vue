<template>
  <v-sheet color="#212135">
    <v-container 
      class="pa-0" 
      height="40"
    >
      <v-app-bar 
        dense 
        flat 
        color="#212135" 
        dark 
        height="40"
      >
        <v-spacer></v-spacer>
        <v-toolbar-items
          class="v-toolbar-items"
        >
          <v-toolbar-title
            class="btn mt-1 ml-12" 
            height="40"
            v-for="link in links"
            :key="link.title"
          >
            <router-link 
              to="/" 
              tag="span" 
              class="pointer" 
              style="color: #EEEEEE; 
              font-size: small;"
            >
              {{ link.title }}
              <v-span 
                style="color: #cb3131; 
                margin-left: 3px"
              >
                {{ link.count }}
              </v-span>
            </router-link>
          </v-toolbar-title>
        </v-toolbar-items>
        <v-divider 
          vertical 
          class="mr-n1"
        >
        </v-divider>
        <v-btn
          color="#212135"
          id="attachMenu"
          :v-bind="buttonName"
          small
          flat
          depressed
          tile
          height="40"
          class="mx-1"
          @click="expand = !expand"
        >
          {{ buttonName }}
        </v-btn>
        <v-divider 
          vertical 
          class="mx-n1"
        ></v-divider>
        <v-menu
          v-model="expand"
          tile
          location="bottom right"
        >
          <v-list class="py-0" 
            color="#212135"
            dark
          >
            <v-list-item
              v-for="lang in languages"
              :key="lang.name"
              @click="changeButtonName(lang.abbr)"
            >
              <v-list-item-title
                style="font-size: smaller;"
              >
                {{ lang.name }}
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar>
    </v-container>
  </v-sheet>
</template>

<script>
export default {
  data: () => ({
    buttonName: 'EN',
    expand: false,
    links: [
      { title: "Bildirişler", count: 99 },
      { title: "Bazar", count: 99 },
      { title: "Habarlar & Media", count: 99 },
    ],
    languages: [
      { name: 'English', abbr: 'EN' },
      { name: 'Русский', abbr: 'RU'  },
      { name: 'Türkmen', abbr: 'TM'  },
    ]
  }),
  methods: {
    changeButtonName(lang) {
      this.buttonName = lang
      console.log(lang)
    }
  },
};
</script>

<style>
.btn {
  text-transform: unset !important;
}
.pointer {
  align-self: center;
}

.v-toolbar-items {
  font-style: normal;
  font-weight: 600;
  font-size: 16px;
  line-height: 100%;
  margin-right: 45px;
  margin-left: 45px;
}
</style>
