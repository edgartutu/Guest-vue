<template>
  <v-container
    fill-height
    fluid
    grid-list-xl>
    <v-layout
      justify-center
      wrap
    >
      <v-flex  xs12
        md12 >
         
        
          <v-form >  
          
            <v-expansion-panel popout>
              <v-expansion-panel-content v-for="proposal in proposals" :key="proposal.supervisor">
                <template v-slot:header>
               <div>{{proposal.title}}</div>
            </template>
                  <v-card-text class="px-16">
                     <h4 class="font-weight-bold">Students</h4>
                    <div >{{proposal.reg_no}}</div>
                     <h4 class="font-weight-bold">Title</h4>
                    <div>{{proposal.title}}</div>
                    <h4 class="font-weight-bold">Problem statment</h4>
                    <div>{{proposal.problem_statement}}</div>
                     <h4 class="font-weight-bold">Abstract</h4>
                    <div>{{proposal.abstract}}</div>
                      <h4 class="font-weight-bold">File</h4>
                    <div>{{proposal.proposal_uploadfile}}</div>
                    <h4 class="font-weight-bold">status</h4>
                    <div>{{proposal.status}}</div>
                    <h4 class="font-weight-bold">Supervisors</h4>
                     <div>{{proposal.supervisor}}</div>
                     <h4 class="font-weight-bold">Comment</h4>
                     <div>{{proposal.commet}}</div>
                   
                  </v-card-text>
          
              </v-expansion-panel-content>
            </v-expansion-panel>
      
    
          </v-form>
        
      </v-flex>
      <v-flex
        xs12
        md4
      >
        
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import axios from 'axios'
export default {
    data () {
      return {
        proposals: []
      }  
    },
    mounted(){
      axios.get('http://127.0.0.1:5000/viewproposals').then(response => {
                this.proposals = response.data
            })
    }
     
    
   
}
</script>
