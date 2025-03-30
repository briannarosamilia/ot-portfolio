<script setup>
import {shallowRef} from 'vue'

defineProps();

// Emit scroll-to event to parent
const emit = defineEmits();

const scrollTo = (section) => {
  console.log(section);
  // Emit event with the section name
  emit('scroll-to', section);
};

const drawer = shallowRef(false)


const items = [
  {
    text: 'Experience',
    section: 'experience',
  },
  {
    text: 'Education',
    section: 'education',
  },
  {
    text: 'Volunteer Experience',
    section: 'education',
  },
  {
    text: 'Portfolio',
    section: 'education',
  },
  {
    text: 'Capstone',
    section: 'education',
  },
  {
    text: 'Skills',
    section: 'education',
  },
]


</script>

<template>
  <v-layout>
    <v-app-bar class="px-md-4" color="surface-variant" flat>
      <template #prepend>
        <v-app-bar-nav-icon
            v-if="$vuetify.display.smAndDown"
            @click="drawer = !drawer"
        />
      </template>

      <img
          src="/ot_logo.png"
          alt="Logo"
          class="me-sm-8"
          style="max-width: 40px"
       />

      <template v-if="$vuetify.display.mdAndUp">
        <v-btn
            v-for="(item, i) in items"
            :key="i"
            class="me-2 text-none"
            slim
            v-bind="item"
            @click="scrollTo(item.section)"
        />
        <v-menu>
          <template v-slot:activator="{ props }">
            <v-btn
                v-bind="props"
                class="me-2 text-none"
                slim
            >
              More
            </v-btn>
          </template>
          <v-list>
            <v-list-item>
              <v-list-item-title>Memberships</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title>Hobbies</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </template>

      <v-spacer />
    </v-app-bar>

    <v-navigation-drawer
        v-if="$vuetify.display.smAndDown"
        v-model="drawer"
        location="top"
        temporary
        width="105"
    >
      <v-list class="py-0" slim>
        <v-list-item link title="Experience" @click="scrollTo('experience')" />

        <v-list-item link title="Education" @click="scrollTo('education')" />

<!--        <v-list-group-->
<!--            prepend-icon="mdi-account-multiple-outline"-->
<!--            title="Customers"-->
<!--        >-->
<!--          <template #activator="{ props: activatorProps }">-->
<!--            <v-list-item v-bind="activatorProps" />-->
<!--          </template>-->

<!--          <v-list-item-->
<!--              link-->
<!--              prepend-icon="mdi-account-plus-outline"-->
<!--              title="Create New"-->
<!--          />-->

<!--          <v-list-group prepend-icon="mdi-magnify" title="Search">-->
<!--            <template #activator="{ props: activatorProps }">-->
<!--              <v-list-item v-bind="activatorProps" />-->
<!--            </template>-->

<!--            <v-list-item-->
<!--                link-->
<!--                prepend-icon="mdi-account-outline"-->
<!--                title="By Name"-->
<!--            />-->

<!--            <v-list-item-->
<!--                link-->
<!--                prepend-icon="mdi-email-outline"-->
<!--                title="By Email"-->
<!--            />-->

<!--            <v-list-item-->
<!--                link-->
<!--                prepend-icon="mdi-phone-outline"-->
<!--                title="By Phone"-->
<!--            />-->
<!--          </v-list-group>-->
<!--        </v-list-group>-->

<!--        <v-list-item link prepend-icon="mdi-calendar" title="Calendar" />-->

<!--        <v-list-item link prepend-icon="mdi-poll" title="Analytics" />-->

<!--        <v-divider />-->

<!--        <v-list-item link prepend-icon="mdi-inbox-outline" title="Inbox" />-->

<!--        <v-list-item-->
<!--            link-->
<!--            prepend-icon="mdi-bell-outline"-->
<!--            title="Notifications"-->
<!--        />-->

<!--        <v-divider />-->

<!--        <v-list-item-->
<!--            lines="two"-->
<!--            link-->
<!--            prepend-avatar="https://vuetifyjs.b-cdn.net/docs/images/avatars/planetary-subscriber.png"-->
<!--            subtitle="Vuetify Engineer"-->
<!--            title="John Leider"-->
<!--        />-->
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-toolbar color="surface" elevation="1" height="84">
        <template #title>
          <h2 class="text-h4 font-weight-bold">Brianna Rosamilia, OTS</h2>
        </template>
      </v-toolbar>

      <div class="pa-4">
        <v-sheet

            rounded="lg"
            width="100%"
            style="height: calc(100vh - 180px); overflow-y: auto; background: linear-gradient(to bottom, #BBDEFB, #E3F2FD)"
        >
          <slot></slot>
        </v-sheet>
      </div>
    </v-main>
  </v-layout>
</template>
