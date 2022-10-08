<template>
  <div class="container">
    <h5>Categories</h5>
    <table class="table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Note</th>
        <th>Balance</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="category in categories" v-bind:key="category.id">
        <td>{{category.name}}</td>
        <td>{{category.note}}</td>
        <td>{{convertMilliUnitsToCurrencyAmount(category.balance).toFixed(2)}}</td>
      </tr>
    </tbody>
    </table>
  </div>
</template>

<script>
// Import utils from YNAB
import {utils} from 'ynab';

export default {
  props: ['categories'],
  methods: {
    // Now we can make this method available to our template
    // So we can format this milliunits in the correct currency format
    convertMilliUnitsToCurrencyAmount: utils.convertMilliUnitsToCurrencyAmount
  }
}
</script>
