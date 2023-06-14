<template>
  <main class="container has-background-light-grey mt-6">
    <div :class="{ 'is-hidden': popUpActive }" class="is-flex is-flex-direction-column columns is-vcentered">
      <h1 class="title has-text-centered has-text-info column is-vcentered">Keyboard Shortcuts</h1>
    <button 
      type="button" 
      @click="togglePopUp"
      class="button is-info is-large is-clickable is-hovered column is-vcentered"
    >
      Open Keyboard Shortcuts
    </button>
    </div>
    <AppPopUp :popUpActive="popUpActive" @close="togglePopUp">
      <div>
        <h1 class="title has-text-centered has-text-info">List of Shortcuts</h1>
        <ul class="has-text-centered">
          <li v-for="(item, index) in items" class="mt-3">
            <kbd>{{ item.firstKey }}</kbd> + <kbd>{{ item.secondKey }}</kbd>
          </li>
        </ul>
      </div>
    </AppPopUp>
  </main>
</template>

<script>
import AppPopUp from './components/AppPopUp.vue'
import { ref } from 'vue'

export default {
  name: "App",
  components: {
    AppPopUp,
  },
  setup() {
    const popUpActive = ref(false);

    const togglePopUp = () => {
      popUpActive.value = !popUpActive.value;
    };

    const items = ref([
      { firstKey: 'Ctrl',
        secondKey: 'A'
      },
      { firstKey: 'Ctrl',
        secondKey: 'C'
      },
      { firstKey: 'Ctrl',
        secondKey: 'E'
      },
      { firstKey: 'Ctrl',
        secondKey: 'F'
      },
      { firstKey: 'Ctrl',
        secondKey: 'L'
      },
      { firstKey: 'Ctrl',
        secondKey: 's'
      },
      { firstKey: 'Ctrl',
        secondKey: 'P'
      },
      { firstKey: 'Ctrl',
        secondKey: 'D'
      },
      { firstKey: 'Ctrl',
        secondKey: 'Y'
      },
      { firstKey: 'Ctrl',
        secondKey: 'Shift'
      },
      { firstKey: 'Ctrl',
        secondKey: 'O'
      },
      { firstKey: 'Ctrl',
        secondKey: 'U'
      },
      { firstKey: 'Ctrl',
        secondKey: 'p'
      },
      { firstKey: 'Ctrl',
        secondKey: 'N'
      },
      { firstKey: 'Ctrl',
        secondKey: 'I'
      },
     
    ]);

    return { popUpActive, togglePopUp, items };
  },
};
</script>

