<template>
  <div class="events container">
    <h2 class="subtitle is-3">
    Wybierz tor
    </h2>
    <div class="columns is-multiline">
      <div v-for="event in events" :event="event" :key="event.id" class="column is-one-quarter">
        <router-link :to="'/event/' + event.id">
          <EventCard :event="event" />
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import EventCard from '@/components/EventCard';
export default {
  name: 'EventsList',
  components : {
    EventCard
  },
  data () {
    return {
      event: {},
      events: [
        {
          id: 1,
          name: 'Tor 1',
          category: 'Karabiny',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius quia aperiam eligendi dolorum reprehenderit ea amet, aliquid dolorem beatae, iste aliquam ullam. Sequi ab eligendi consectetur neque laudantium, libero asperiores.',
          featuredImage: 'https://images.unsplash.com/photo-1577905027788-c9fc420bbad9?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
          images: [
            'https://images.unsplash.com/photo-1577905027788-c9fc420bbad9?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80',
          ],
          location: '',
          date: 'Karabiny',
          time: ''
        },
        {
          id: 2,
          name: 'Tor 2',
          category: 'Broń biała',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius quia aperiam eligendi dolorum reprehenderit ea amet, aliquid dolorem beatae, iste aliquam ullam. Sequi ab eligendi consectetur neque laudantium, libero asperiores.',
          featuredImage: 'https://wearememphis.com/wp-content/uploads/2019/05/920x920.jpg',
          images: [
            'https://wearememphis.com/wp-content/uploads/2019/05/920x920.jpg'
          ],
          location: '',
          date: 'Broń biała',
          time: ''
        },
        {
          id: 3,
          name: 'Tor 3',
          category: 'Broń miotająca',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius quia aperiam eligendi dolorum reprehenderit ea amet, aliquid dolorem beatae, iste aliquam ullam. Sequi ab eligendi consectetur neque laudantium, libero asperiores.',
          featuredImage: 'https://media-cdn.tripadvisor.com/media/photo-s/14/c3/64/9c/4444.jpg',
          images: [
            'https://media-cdn.tripadvisor.com/media/photo-s/14/c3/64/9c/4444.jpg'
          ],
          location: '',
          date: 'Broń miotająca',
          time: ''
        },
        {
          id: 4,
          name: 'Tor 4',
          category: 'Pistolety',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius quia aperiam eligendi dolorum reprehenderit ea amet, aliquid dolorem beatae, iste aliquam ullam. Sequi ab eligendi consectetur neque laudantium, libero asperiores.',
          featuredImage: 'https://g8.gazetaprawna.pl/p/_wspolne/pliki/3255000/3255015-strzelnica-pistolet.jpg',
          images: [
            'https://g8.gazetaprawna.pl/p/_wspolne/pliki/3255000/3255015-strzelnica-pistolet.jpg'
          ],
          location: '',
          date: 'Pistolety',
          time: ''
        }
      ]
    }    
  }
}
</script>
<style lang="scss" scoped>
  .events {
    margin-top: 100px;
    text-align: center;
  }
</style>