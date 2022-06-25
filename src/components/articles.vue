<template>
<div v-for="(producto, index) in product" :key="index" class="col-lg-3 col-md-6 col-sm-12 col-xs-12 my-lg-1 my-md-1 my-sm-1">
            <div class="card h-100 sh">
              <div class="row p-2 mx-auto">
                <div class="col-12">
                  <img v-bind:src="producto.img_url" class="img-fluid" v-bind:alt="producto.name"
                    v-bind:title="producto.name" />
                </div>
              </div>
              <div class="card-body p-0 d-flex justify-content-between flex-column">
                <div class="row">
                  <div class="col-12 py-0 px-4">
                    <p class="card-text text-capitalize text-lg-start text-sm-center">
                      {{ producto.name }}
                    </p>
                  </div>
                </div>
                <div class="row align-content-end m-0 w-100 text-end">
                  <div class="col-12 p-0">
                    <img class="mb-2" v-bind:src="producto.img_url_state"  v-bind:alt="producto.text_state"
                       v-bind:title="producto.text_state" />
                  </div>
                </div>
              </div>
            </div>
          </div>

<!--
<div>
    <div v-for="(producto, index) in product" :key="index"><h1>{{ producto.name }}</h1></div>
</div>-->

</template>

<script>
import Data from '../js/data.json'

export default {
  components:{
    Data,
  },
	setup() {
    const product = Data.products;
    
		return {
      product
      
		};
	},
};
</script>

<style>
</style>
