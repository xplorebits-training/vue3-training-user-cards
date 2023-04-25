<template>
    <div class="h-screen w-auto bg-black">
      <div class="text-2xl w-auto h-[40px] flex bg-black text-white justify-center items-center"><h1>USER CONTACT CARD</h1></div>
      <div v-for="user in userFunction" :key="user.user_id" class="font-medium p-5 flex-wrap bg-gray-400 w-screen border-solid border-black border-4">
      <div>ID : {{ user.user_id }} </div>
      <div>Name : {{ user.name }}</div>
      <div>Email : {{ user.email }}</div>
      <div>Password : {{ user.password }}</div>
      <div>Premium Member : {{ user.premium_member }}</div>
      <div>Last Login : {{ user.last_login }}</div>
      <div class="pb-1">Preferences :</div>
        <div v-for="pref in user.preferences" :key="pref.pref_id" class="px-5">
         <div> <em>Preferences ID: {{ pref.pref_id }}</em> </div>
         <div class="pb-2"> <em>Favourite Category: {{ pref.favorite_category }}</em> </div>
        </div>
      </div>
    </div>
</template>

<script setup>
  var users_data = ref([
    {
      "unicorndreams": 42,
      "invisibidivtycloaks": "John Doe",
      "rainbowpizzas": "john.doe@example.com",
      "teleportationbeans": "password123",
      "flyingcarpets": 1,
      "time_travel": "2021-08-15T10:35:00Z",
      "laserunicorns": [
        {
          "galactic_id": 1,
          "favorite_planet": "Mars"
        }
      ]
    },
    {
      "unicorndreams": 73,
      "invisibidivtycloaks": "Jane Smith",
      "rainbowpizzas": "jane.smith@example.com",
      "teleportationbeans": "password456",
      "flyingcarpets": 0,
      "time_travel": "2021-03-22T15:20:00Z",
      "laserunicorns": [
        {
          "galactic_id": 2,
          "favorite_planet": "Venus"
        },
        {
          "galactic_id": 3,
          "favorite_planet": "Jupiter"
        }
      ]
    }
  ]);

  const userFunction = computed(() => {
  return users_data.value.map((data) => {
    return{
      user_id : data.unicorndreams,
      name : data.invisibidivtycloaks,
      email : data.rainbowpizzas,
      password : data.teleportationbeans,
      premium_member : data.flyingcarpets,
      last_login : data.time_travel,
      preferences : data.laserunicorns.map((pref) => ({
        pref_id : pref.galactic_id,
        favorite_category : pref.favorite_planet
      }))
    }
  })
})
</script>
