# vue3-training-user-cards
Vue3 Composition API training: Computed on user cards

Lets consider following user data:

``` json
[
  {
    "unicorndreams": 42,
    "invisibilitycloaks": "John Doe",
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
    "invisibilitycloaks": "Jane Smith",
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
]
```

The above data as absurd object keys. By keeping the orignal data as it is, create a page that display user contact card with all the above information displayed.
Use Vue computed properties to define new data from the above original data.

The logical object keys are:
* unicorndreams -> user_id
* invisibilitycloaks -> name
* rainbowpizzas -> email
* teleportationbeans -> password
* flyingcarpets -> premium_member
* time_travel -> last_login
* laserunicorns -> preferences
* galactic_id -> pref_id
* favorite_planet -> favorite_category
