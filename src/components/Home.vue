<template>
  <div class="home">
    <md-card>
      <md-card-header>
        <div class="md-title">
          Material Design With VueJs 2 Demo
        </div>
        <div class="md-subhead">
          by CodingTheSmartWay.com
        </div>
      </md-card-header>
      <md-card-content>
        <md-button
          class="md-raised md-primary"
          v-on:click="fillTable()">
          Fill Table
        </md-button>
        <md-button
          class="md-raised md-primary"
          v-on:click="clearTable()">
          Clear Table
        </md-button>
      </md-card-content>
      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>
              First Name
            </md-table-head>
            <md-table-head>
              Last Name
            </md-table-head>
            <md-table-head>
              Email
            </md-table-head>
          </md-table-row>
        </md-table-header>
        <md-table-body>
          <md-table-row
            v-for="contact in contacts">
            <md-table-cell>
              {{ contact.firstname }}
            </md-table-cell>
            <md-table-cell>
              {{ contact.lastname }}
            </md-table-cell>
            <md-table-cell>
              {{ contact.email }}
            </md-table-cell>
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      contacts: []
    }
  },
  methods: {
    fillTable: function() {
      this.contacts.push({firstname: 'Earl', lastname: 'Stevens', email: 'earl@stevens.com'});
      this.contacts.push({firstname: 'Sean', lastname: 'Carter', email: 'sean@carter.com'});
      this.contacts.push({firstname: 'Brad', lastname: 'Jordan', email: 'brad@jordan.com'});
    },
    clearTable: function() {
      this.contacts.splice(0, this.contacts.length);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /*margin-top: 60px;*/
  margin-left: 30px;
  margin-right: 30px;
</style>
