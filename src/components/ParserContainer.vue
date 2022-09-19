<template>
  <v-container>
    <v-card
    elevation="2"
    class="mt-8 mx-auto pa-4 rounded-lg"
    >
    <v-row>
      <v-col><p style="font-size: 22px;" class="text-center font-weight-medium">Please type in your query or select one from the predefined list</p></v-col>
    </v-row>
    <v-row class="justify-center">
      <v-col cols="12" md="8" lg="9">
        <v-text-field v-model="sqlQuery" label="Query" clearable hint="Please enter a valid SQL Query" :disabled="showData" @click="onClickClearQuery()" dense outlined> </v-text-field>
      </v-col>
    </v-row>
    <v-row class="justify-center">
      <v-col cols="12" md="4" lg="6">
        <v-select label="Predefined Queries" :items="predefinedQueries" v-model="sqlQuery" :disabled="showData" solo dense></v-select>
      </v-col>
      <v-col cols="12" md="4" sm="3" lg="3" class="mt-3 mb-3">
        <v-row class="justify-center">
          <v-btn class="mr-2" pt-2 :disabled="!isSQLqueryEmpty" @click="onRunQuery()" color="primary">Run Query</v-btn>
          <v-btn pt-2 :disabled="!isSQLqueryEmpty" @click="onClickClearQuery()">Clear Results</v-btn>
        </v-row>
      </v-col>
    </v-row>
    </v-card>
    <v-card v-if="showData" elevation="2"
        class="mt-8 mx-auto pa-4 rounded-lg">
        <result-component v-if="showData" :query="sqlQuery"></result-component>
    </v-card>
  </v-container>
</template>
<script lang="ts">
import Vue from 'vue';
import { Component } from 'vue-property-decorator';
import ResultComponent from './ResultComponent.vue';
import sqlQueryList from './configs';

@Component({
  components: {
    ResultComponent,
  },
})
export default class ParserContainer extends Vue {
  public sqlQuery = '';

  public showData = false;

  get isSQLqueryEmpty() {
    return this.sqlQuery;
  }

  get predefinedQueries() {
    return sqlQueryList;
  }

  onRunQuery() {
    this.showData = true;
  }

  onClickClearQuery() {
    this.showData = false;
    this.sqlQuery = '';
  }
}

</script>
