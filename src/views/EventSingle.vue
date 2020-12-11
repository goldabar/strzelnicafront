<template>
  <div class="event-single">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            {{ event.name }}
          </h1>
          <date-picker placeholder="Wybierz datę" format="DD-MM-YYYY HH:mm" :time-picker-options="{start: '08:00', step:'00:60', end: '21:00'}" v-model="time2" type="datetime"></date-picker>
          <h2 class="subtitle ">
            <strong v-if="time2 !== null">Data rezrwacji:</strong> {{time2}}
            <br>
           <!-- <strong>Godzina:</strong> {{ event.time }} -->
          </h2>
        </div>
      </div>
    </section>
    <section class="event-content">
      <div class="container">
        <p class="is-size-4 description">{{ event.description }}</p>
        <p class="is-size-5"><strong>Lokacja:</strong> {{ event.location }}</p>
        <p class="is-size-5"><strong>Kategoria:</strong> {{ event.category }}</p>
        <div class="event-images columns is-multiline has-text-centered">
          <div v-for="image in event.images" :key="image.id" class="column is-one-third">
            <img :src="image" :alt="event.name">
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import DatePicker from 'vue2-datepicker';
import 'vue2-datepicker/index.css';
export default {
  components: {
    DatePicker
  },
  name: 'EventSingle',
  data () {
    return {
      time2: null,
      disabledDates: {
        
      },
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
          location: 'ul. Szkolna 17, Warszawa',
          date: '12-25-2020',
          time: '11:30'
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
          location: 'ul. Szkolna 17, Warszawa',
          date: '11-21-2020',
          time: '12:00'
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
          location: 'ul. Szkolna 17, Warszawa',
          date: '11-21-2020',
          time: '12:00'
        },
        {
          id: 4,
          name: 'Tor 4',
          category: 'Pisotlety',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eius quia aperiam eligendi dolorum reprehenderit ea amet, aliquid dolorem beatae, iste aliquam ullam. Sequi ab eligendi consectetur neque laudantium, libero asperiores.',
          featuredImage: 'https://g8.gazetaprawna.pl/p/_wspolne/pliki/3255000/3255015-strzelnica-pistolet.jpg',
          images: [
            'https://g8.gazetaprawna.pl/p/_wspolne/pliki/3255000/3255015-strzelnica-pistolet.jpg'
          ],
          location: 'ul. Szkolna 17, Warszawa',
          date: '11-21-2020',
          time: '12:00'
        }
      ],
      event: {}
    }    
  },
  created() {
    const ID = Number(this.$route.params.id);
    let event = this.events.find(event => event.id === ID);
    this.event = event;
  }
}
</script>