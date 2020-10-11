<template>
  <div class="displayTopics">
    <div class="title">Please Selecte Subject</div>
    
    <span v-for="(s, index) in subjects.subjects" :key="index">
      <input type="radio" name="Subjects" :id="s.subject" :value="s.subject" @click="ShowTopics(s)">
        <label :for="s">{{s.subject}}</label>
    </span>
      <br><br>
    <div v-if="topics.length !== 0">
      <div class="title">Please Select Topic</div>
        <span v-for="t in topics" :key="t">
        <input type="radio" :name="t" :id="t" :value="t">
        <label :for="t">{{t}}</label>
    </span>
    </div>

  </div>
</template>

<script>

import { subjects } from './../data/subjects.js'

export default {
  name: 'SubjectList',
  props: {
    msg: String
  },
  data() {
    return {
      subjects : subjects,
      topics:[]
    }
  },
  methods:{
    ShowTopics(subject){
      console.log(this.topics);
      this.topics = subject.Topics;
      console.log(this.topics);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.displayTopics{
  text-align: left;
  background-color:navajowhite;
  margin: 5px;  
}
.title{
  font-family: 'Courier New', Courier, monospace;
  font-weight: bold;
  font-size: 20px;
  margin: 5px;
}
</style>
