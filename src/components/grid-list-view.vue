<template lang="html">

	<section class="grid-list-view">
		<div class="grid--list--container">
			<div id="grid--list--button">
				<div class="button active"><i class="fas fa-bars"></i> List</div> 
				<div class="button"><i class="fas fa-th-large"></i> Grid</div>
				<div class="button"><i class="fas fa-th"></i> Grid Max</div>
			</div>
			<div id="grid--list--element--container">
				<slot></slot>
			</div>
		</div>
	</section>

</template>

<script>

import './../../node_modules/@fortawesome/fontawesome-free/css/fontawesome.min.css';
import './../../node_modules/@fortawesome/fontawesome-free/css/all.min.css';

	export default {
		name: 'grid-list-view',
		props: [],
		mounted () {
			var elements = document.getElementsByClassName("grid--list--element");
			var i;

			function listView() {
				for (i = 0; i < elements.length; i++) {
					elements[i].style.width = "100%";
				}
			}

			function gridView() {
				for (i = 0; i < elements.length; i++) {
					elements[i].style.width = "50%";
				}
			}

			function gridViewMax() {
				for (i = 0; i < elements.length; i++) {
					elements[i].style.width = "33.33%";
				}
			}

			var button = document.getElementsByClassName("button");

			button[0].addEventListener("click", function(){
				listView();
			});

			button[1].addEventListener("click", function(){
				gridView();
			});

			button[2].addEventListener("click", function(){
				gridViewMax();
			});

			var container = document.getElementById("grid--list--button");
			var btns = container.getElementsByClassName("button");
			for (i = 0; i < btns.length; i++) {
				btns[i].addEventListener("click", function() {
					var current = document.getElementsByClassName("active");
					current[0].className = current[0].className.replace(" active", "");
					this.className += " active";
				});
			}
		},
		data () {
			return {

			}
		},
		methods: {

		},
		computed: {

		}
}


</script>

<style scoped lang="scss">
.grid-list-view {

}

* {
	box-sizing: border-box;
}

.grid--list--element {
	float: left;
	width: 100%;
	padding: 10px;
	background-color: #eee;
	color: #000;
	border: 0.5px solid #000;
}


.row::after{
	content: "";
	display: table;
	clear: both;
}

.grid--list--button {
	display: inline-block;
	width: 100%;
}

.button {
	border: none;
	outline: none;
	padding: 12px 16px;
	background-color: #f1f1f1;
	cursor: pointer;
	width: 33.33%;
	min-height: 25px;
	float: left;
}

.button:hover {
	background-color: #ddd;
}

.button.active {
	background-color: #666;
	color: white;
}
</style>
