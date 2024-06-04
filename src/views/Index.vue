<template>
	<Header></Header>
	<Loading :showLoading="showLoading" />
	<div>
		<!-- 页面内容 -->
		<div class="container">
			<img class="banner" src="../assets/images/banner.png" mode=""></img>
			<div class="uni-form-item uni-column">
				<div class="title">Upload your photos</div>
				<div class="content">
					<div class="upload upload-before">
						<img class="uploadIcon" src="../assets/icons/uploadImg.png" mode=""></img>
						<text>limit 30MB per file</text>
					</div>

					<div class="upload upload-done" v-if="imgUrl">
						<img class="upload-res" :src="imgUrl" mode=""></img>
						<img class="deleteIcon" src="../assets/icons/delete.png" mode=""></img>
					</div>
				</div>
			</div>

			<div class="uni-form-item uni-column">
				<div class="title">Customize your clothing logo</div>
				<div class="content">
					<input v-model="logoText" name="input" placeholder="Please enter the logo text on your clothes" />
				</div>
			</div>

			<div class="uni-form-item error-text" v-if="showError">
				<div class="content">Please Upload your photos</div>
			</div>
			<div class="bottom_btn">
				<div class="spendCount">
					<img class="icon" src="../assets/icons/money.png" mode=""></img>
					<text>-8</text>
				</div>
				<button class="submitBtn" @click="formSubmit">
					<text>Generate img</text>
				</button>
			</div>


		</div>
	</div>
</template>

<script setup>
import {
	ref,
} from 'vue';
import Header from '../components/Header.vue';
import Loading from '../components/Loading.vue';
const showLoading = ref(false);
const showError = ref(false);
const logoText = ref('');
const imgUrl = ref('');
const imgId = ref(''); // 存储图片ID

const formSubmit = () => {
	if (!logoText.value) {
		showError.value = true

		setTimeout(() => {
			showError.value = false
		}, 3000)
		return
	}
	showLoading.value = true
	setTimeout(() => {
		showLoading.value = false
	}, 3000)
}

</script>

<style scoped>
.banner {
	width: 100%;
	height: 27.73vw;
	margin-top: 8.53vw;

	margin-bottom: 8.53vw;
}

.uni-form-item .title {
	font-family: Roboto-Bold;
	font-weight: bold;
	font-size: 3.73vw;
	color: #000000;
	text-align: left;
	font-style: normal;
	text-transform: none;
	margin-bottom: 2.13vw;
}

.uni-form-item {
	margin-bottom: 8.53vw;
}

.uni-form-item .content {
	width: 100%;
	height: 14.93vw;
	background: #F1F1F1;
	border-radius: 1.07vw;
	display: flex;
	align-items: center;
	padding: 0 3.2vw;
	box-sizing: border-box;

}

.error-text .content {
	background-color: #F3A32B;
	font-size: 3.2vw;
	color: #fff;
}

.uni-form-item .content input {
	width: 100%;
	font-size: 3.2vw;
	font-family: Roboto-Regular;
	border: none;
	outline: none;
	background-color: #F1F1F1;
}

.upload {
	width: 100%;
	display: flex;
	align-items: center;
}

.upload-before text {
	color: #575757;
	font-size: 3.2vw;
	font-family: Roboto-Regular;
}

.upload-done {
	justify-content: space-between;
}

.uploadIcon {
	width: 6.4vw;
	height: 6.4vw;
	margin-right: 2.13vw;
}

.upload-res {
	width: 6.4vw;
	height: 8.53vw;
}

.deleteIcon {
	height: 5.07vw;
	width: 5.07vw;
}


.bottom_btn .spendCount {
	width: 19.2vw;
	height: 9.07vw;
	background: #F1F1F1;
	border-radius: 1.07vw;
	display: flex;
	justify-content: center;
	align-items: center;
}

.bottom_btn .spendCount .icon {
	height: 6.4vw;
	width: 6.4vw;
	margin-right: 1.07vw;
}

.bottom_btn .submitBtn {
	width: 64.8vw;
	height: 9.07vw;
	background: #000000;
	box-shadow: 1.07vw 1.07vw 2.13vw .13vw rgba(0, 0, 0, 0.32);
	border-radius: 1.07vw;
	display: flex;
	justify-content: center;
	align-items: center;

}

.bottom_btn .submitBtn text {
	font-size: 3.73vw;
	font-weight: bold;
	background: linear-gradient(182deg, #2F54EB 0%, #FF26A8 100%);
	-webkit-background-clip: text;
	color: transparent;
	background-clip: text;
}
</style>
