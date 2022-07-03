<template>
<!--Nav-->
<div class="container">
	<div class="row">
    	<nav class="navbar navbar-expand-md navbar-light mb-4 p-0">
        	<div class="col-lg-5 col-md-6 col-sm-12 col-xs-12 w-auto">
            	<a class="navbar-brand" href="#">
                	<img src="../../public/img/logo_akemi.png" class="img-fluid d-lg-inline-block d-md-inline-block d-sm-none d-xs-none small" alt="Akemi" title="Akemi" />
                	<img src="../../public/img/logo_akemi_xs.png" class="img-fluid d-lg-none d-md-none d-sm-inline-block d-xs-inline-block" alt="Akemi" title="Akemi" />
              	</a>
            </div>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            	<span class="navbar-toggler-icon"></span>
            </button>
            <div id="navbarSupportedContent" class="collapse navbar-collapse text-nowrap mx-0">
            	<div class="container my-4 p-0">
                	<div class="offset-lg-6 col-lg-6 col-md-6 col-sm-12 d-md-flex d-md-inline-block justify-content-lg-end">
                		<div class="col bg-light my-0 mx-0 pe-2">
                    		<div class="nav navbar-nav me-lg-5 my-lg-2 me-md-3 my-md-0 py-1">
                    			<a class="nav-item nav-link active ps-3 pe-3 py-0 my-0" href="#">PRODUCTS</a>
                      			<a class="nav-item nav-link ps-3 pe-3 py-0 my-0" href="#">BRANDS</a>
                      			<a class="nav-item nav-link ps-3 pe-3 py-0 my-0" href="#">AKEMI SETS</a>
                    		</div>
                  		</div>
                  		<div class="col bg-light my-0 mx-0 pe-2">
                    		<div class="nav navbar-nav me-lg-5 my-lg-2 me-md-3 my-md-0 py-1">
                      			<a class="nav-item nav-link ps-3 pe-3 py-0 my-0" href="#">ABOUT US</a>
                      			<a class="nav-item nav-link ps-3 pe-3 py-0 my-0" href="#">REGISTER</a>
                      			<a class="nav-item nav-link ps-3 pe-3 py-0 my-0" href="#">LOGIN</a>
                    		</div>
                  		</div>
                  		<div class="col bg-dark my-0 mx-0 pe-2">
                    		<div class="nav navbar-nav me-lg-5 my-lg-2 me-md-3 my-md-0 py-1">
                      			<a class="nav-item nav-link text-white ps-3 pe-3 py-0 my-0" href="#">CART</a>
                      			<a class="nav-item nav-link text-white ps-3 pe-3 py-0 my-0" href="#">{{ qty }} Items</a>
                      			<a class="nav-item nav-link text-white ps-3 pe-3 py-0 my-0" href="#">{{ total.toFixed(2) }}€</a>
                    		</div>
                  		</div>
                	</div>
              	</div>
            </div>
        </nav>
    </div>
</div>
<!--Banner-->
<div class="container m-0 p-0">
    <div class="row m-0 sh">
        <div class="col-12 p-2 bg-white border">
            <img src="../../public/img/banner1.png" class="img-fluid w-100" alt="Promo" title="Promo" />
        </div>
    </div>
</div>
<!--Productos-->
<div class="container m-0 p-0">
    <div class="row my-4">
        <div class="col-6">
            <img src="../../public/img/new_products.png" alt="New Products" />
        </div>
    </div>
	<div class="row">
<!--generacion de productos dinamico-->
	<div v-on:click="isHidden = !isHidden, indice = index" v-for="(producto, index) in product" :key="index" class="col-lg-3 col-md-6 col-sm-12 col-xs-12 my-lg-1 my-md-1 my-sm-1">
		<div class="card h-100 sh">
			<div class="row p-2 mx-auto">
				<div class="col-12">
					<img v-bind:src="producto.img_url" class="img-fluid" v-bind:alt="producto.name" v-bind:title="producto.name"/>
				</div>
			</div>
			<div class="card-body p-0 d-flex justify-content-between flex-column">
				<div class="row">
					<div class="col-12 py-0 px-4">
						<p class="card-text text-capitalize text-lg-start text-sm-center">{{ producto.name }}</p>
					</div>
				</div>
				<div class="row align-content-end m-0 w-100 text-end">
					<div class="col-12 p-0">
						<img class="mb-2" v-bind:src="producto.img_url_state" v-bind:alt="producto.text_state" v-bind:title="producto.text_state"/>
					</div>
				</div>
			</div>
		</div>
	</div>
	</div>
<!--modal-->
	<div v-if="!isHidden" class="modal-overlay container p-0">
		<div class="position-absolute top-50 start-50 translate-middle w-modal m-0 bg-white">
			<div class="card h-100">
				<div class="row">
					<div class="col-12 p-sm-0">
						<svg v-on:click="isHidden = true" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-x-circle-fill close bg-white" viewBox="0 0 16 16">
							<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293 5.354 4.646z"/>
						</svg>
					</div>
				</div>
				<div class="row d-flex justify-content-center">
					<div class="col-12 containerdiv">
						<img class="p-md-3 p-sm-3 w-100 img-fluid" v-bind:src="product[indice].img_url" v-bind:alt="product[indice].name" v-bind:title="product[indice].name"/>
						<img class="me-sm-1 cornerimage mb-sm-2 img-fluid" v-bind:src="product[indice].img_url_state" v-bind:alt="product[indice].text_state" v-bind:title="product[indice].text_state"/>
					</div>
				</div>
				<div class="card-body p-sm-0 d-flex flex-column justify-content-around">
					<div class="row h-sm-100 px-3">
						<div class="col-12 d-flex flex-column justify-content-center">
							<p class="fw-bold m-sm-0 mb-sm-3 card-text text-capitalize text-center mx-5">{{ product[indice].name }}</p>
							<p class="card-text text-capitalize text-center text-primary">{{ product[indice].price }}€</p>
						</div>
					</div>
					<div class="mx-auto row input-group d-flex justify-content-center mb-2">
						<div class="col-3 p-sm-0 ms-sm-3 me-sm-1">
							<input id="numberInput" value="1" type="number" class="py-sm-1 int-sh bg-light form-control" min="1" step="1" pattern="[0-9]" onkeypress="return event.charCode >= 48 && event.charCode <= 57"/>
						</div>
						<div class="ms-lg-2 ms-sm-2 p-0 col-6 input-group-append">
							<button v-on:click="myCart(product[indice].price),isHidden = true" class="w-100 px-md-5 px-sm-4 py-sm-1 btn-add btn btn-outline-secondary text-uppercase bg-dark text-white" type="button">comprar</button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
	<!--********************************************-->
</div>
</template>

<style>
</style>

<script>
import Data from "../js/data.json";

export default {
	components: {
		Data,
	},
	methods: {
        myCart(price) {
			// items a añadir al carrito
			let num = document.getElementById("numberInput").value
			// valor total del carrito
			this.total = this.total + (price*num)
			// items totales del carrito
			this.qty = parseFloat(num) + parseFloat(this.qty)
		
        },
    },

	data() {
		// comprar
		let qty = 0;
		let total = 0;
		//productos
		const product = Data.products;
		//modal
		let isHidden = true;
		let indice = '';
		return {
			qty,
			total,
			product,
			isHidden,
			indice,
		};
	},
	
};
</script>



