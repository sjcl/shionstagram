<template>
	<div class="card">
		<div class="card-header">
			<img
				class="avatar"
				src="https://yt3.ggpht.com/AyUL9W0ltc_aJr_MysuZBx8hRfb1SIVNREgU9kiOO-lqmdhYkEsllmhagertVIwHwa3UAAKy=s88-c-k-c0x00ffffff-no-rj"
			/>
			<div class="sender">
				<h4 class="name">{{ name }}</h4>
				<p class="location">{{ userLocation }}</p>
			</div>
			<img class="more" src="../assets/icons/more.svg" />
		</div>
		<div class="card-body">
			<p>{{ messagePreview }}</p>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		name: String,
		userLocation: String,
		message: {
			type: String,
		},
	},
	computed: {
		messagePreview() {
			return this.message.length > 110
				? this.message.substring(0, 110) + "..."
				: this.message;
		},
	},
};
</script>

<style scoped>
.card {
	display: flex;
	flex-direction: column;
	border-radius: 0.5rem;
	box-shadow: 0 0.25rem 0.5rem rgba(0, 0, 0, 0.15);
	overflow: hidden;
	cursor: pointer;
}

.card-header {
	display: flex;
	align-items: center;
	padding: 0.5rem 1rem;
	background-color: #ffffff;
}

.avatar {
	width: 3rem;
	height: 3rem;
	border-radius: 50%;
}

.sender {
	margin-left: 0.5rem;
}

.more {
	margin-left: auto;
}

.location {
	font-size: 0.75rem;
	color: #ada6ad;
}

.card-body {
	background-color: var(--purple-800);
	background-image: linear-gradient(
		135deg,
		var(--purple-600) 0%,
		hsl(318, 44%, 75%) 100%
	);
	background-size: 100% 100%;
	background-repeat: no-repeat;
	color: white;
	width: 100%;
	height: 100%;
	padding: 2rem 1rem;
	aspect-ratio: 6 / 5;
	overflow: hidden;
}

.card-body p {
	font-size: 1.5rem;
}
</style>
