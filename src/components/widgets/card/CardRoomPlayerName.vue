<template>
  <v-card color="#061422">
    <v-card-title>
      <span id="card-title">Type a player name.</span>
    </v-card-title>
    <v-card-text>
      <v-container>
        <v-row>
          <v-col cols="12">
              <v-text-field 
                dark
                maxlength="10"
                v-model="playerName"></v-text-field>
           </v-col>       
        </v-row>
      </v-container>
    </v-card-text>
    <v-card-actions>
      <div class="flex-grow-1"></div>
      <v-btn
        dark
        depressed
        color="#FF5252"
        @click="setPlayerName">NEXT</v-btn>
      <v-btn
        dark
        depressed
        color="#43B581"
        @click="cancel">CANCEL</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  export default {
    data() {
      return {
        playerName: '',     
      }
    },
    methods: {
      setPlayerName() {
        // Pass room name to parent component
        this.$emit('setPlayerName', this.playerName)
      },
      cancel() {
        this.$emit('cancel')
      }
    }
  }
</script>

<style scoped>
  #card-title {
    font-size: 16px;
    font-weight: 500;
    color: #FFFFFF;
    opacity: 0.9;
  } 
</style>