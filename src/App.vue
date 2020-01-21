<template>
  <div id="app" class="md:p-5 p-2 mt-3 flex items-center justify-between min-h-screen bg-gray-200">
    
<div class="w-full max-w-md text-center">
    <p class="mb-2 text-gray-700 font-semibold font-sans tracking-wide">List 1</p>
    <draggable tag="ul"
                group="all-users"
               ghost-class="moving-card"
               :list="users"
               :animation="200">
        <HelloWorld v-for="user in users"
                   :user="user"
                   :key="user.id"
                   @on-edit="onEdit"
                   @on-delete="onDelete">
        </HelloWorld>
    </draggable>
</div>



<div class="w-full max-w-md text-center">
    <p class="mb-2 text-gray-700 font-semibold font-sans tracking-wide">List 2</p>
    <draggable tag="ul"
                group="all-users"
               ghost-class="moving-card"
               :list="userss"
               :animation="200">
        <HelloWorld v-for="user in userss"
                   :user="user"
                   :key="user.id"
                   @on-edit="onEdit"
                   @on-delete="onDelete">
        </HelloWorld>
    </draggable>
</div>


<div class="w-full max-w-md text-center">
    <p class="mb-2 text-gray-700 font-semibold font-sans tracking-wide">List 2</p>
    <draggable tag="ul"
                group="all-users"
               ghost-class="moving-card"
               :list="newUsers"
               :animation="200">
        <HelloWorld v-for="user in newUsers"
                   :user="user"
                   :key="user.id"
                   @on-edit="onEdit"
                   @on-delete="onDelete">
        </HelloWorld>
    </draggable>
</div>


   
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
// import { EditIcon, Trash2Icon } from "vue-feather-icons";
import Draggable from 'vuedraggable';

export default {
  name: 'app',

  mounted(){
    console.log(this.users);
  },

  components: {
    HelloWorld,
    // EditIcon,
    // Trash2Icon,
    Draggable
  },

  methods: {
    onEdit(user) {
      alert(`Editing ${user.name}`);
    },
    onDelete(user) {
      alert(`Deleting ${user.name}`);
    }
  },

  data() {
  return {
    userss:[
    ],
    users: [
      {
        id: 1,
        name: "Adrian Schubert",
        avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
      },
      {
        id: 2,
        name: "Violet Gates",
        avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
      },
      {
        id: 3,
        name: "Steve Jobs",
        avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
      },
      {
        id: 4,
        name: "Yassine Smith",
        avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
      },
      {
        id: 5,
        name: "Senior Saez",
        avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
      }
    ],

    newUsers: [
      {
        id: 6,
        name: "Adrian Schubert",
        avatar: "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png"
      },
      {
        id: 7,
        name: "Violet Gates",
        avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png"
      },
      {
        id: 8,
        name: "Steve Jobs",
        avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png"
      },
      {
        id: 9,
        name: "Yassine Smith",
        avatar: "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png"
      },
      {
        id: 10,
        name: "Senior Saez",
        avatar: "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png"
      }
    ]
  }
},

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.moving-card {
  @apply opacity-50 bg-gray-100 border border-blue-500;
}
</style>
