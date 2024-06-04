<template>
	<div class="">
		<Header></Header>


		<div class="container created">
			<img class="res_img" src="../assets/icons/example1.jpg" mode=""></img>

			<div class="download">
				<img src="../assets/icons/download.png" mode=""></img>
			</div>
			<div class="bottom_btn">
				<button class="createMore" @click="goToCreate">Generate More</button>
				<button class="shareBtn">Share</button>
			</div>
		</div>
	</div>
</template>

<script setup>
import {
	ref
} from 'vue';
import { useRouter } from 'vue-router'
import Header from '../components/Header.vue';
const router = useRouter()
function goToCreate (){
	router.push({
		path: '/'
	})
}
</script>

<style scoped>
.created {
	padding-top: 8.53vw;
	height: 100%;
	display: flex;
	justify-content: center;
	align-items: center;
}

.res_img {
	width: 100%;
	height: 116.27vw;
}

.download {
	position: fixed;
	bottom: 23.73vw;
	left: 50%;
	transform: translateX(-50%);
	width: 10.67vw;
	height: 10.67vw;
	border-radius: 100%;
	background: #F1F1F1;
	display: flex;
	justify-content: center;
	align-items: center;
}

.download img {
	height: 4.27vw;
	width: 4.27vw;
}

button {
	font-family: Roboto-Black;
	font-weight: 900;
	font-size: 3.73vw;
	color: #FFFFFF;
	text-align: center;
	font-style: normal;
	text-transform: none;
}

.createMore {
	width: 50.67vw;
	height: 9.07vw;
	background: #000000;
	box-shadow: 1.07vw 1.07vw 2.13vw .13vw rgba(0, 0, 0, 0.32);
	border-radius: 1.07vw;
}

.shareBtn {
	width: 32.27vw;
	height: 9.07vw;
	background: #2F54EB;
	box-shadow: 1.07vw 1.07vw 2.13vw .13vw rgba(47, 84, 235, 0.32);
	border-radius: 1.07vw;
}
</style>
