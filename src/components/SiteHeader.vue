<template>
	<header>
		<router-link to="/">
			<img class="nav-logo" src="../assets/images/Logo.png" alt="" />
		</router-link>

		<div class="nav-icons">
			<select name="locale" v-model="locale">
				<option value="ja">ja</option>
				<option value="en">en</option>
			</select>

			<router-link to="/">
				<img class="icon" src="../assets/icons/Reels.svg" />
			</router-link>
			<router-link to="/profile">
				<img class="icon" src="../assets/icons/Notifiations.svg" />
			</router-link>
			<router-link to="/submit">
				<img class="icon" src="../assets/icons/Send.svg" />
			</router-link>
			<router-link to="/profile">
				<img
					class="profile-img"
					src="https://yt3.ggpht.com/AyUL9W0ltc_aJr_MysuZBx8hRfb1SIVNREgU9kiOO-lqmdhYkEsllmhagertVIwHwa3UAAKy=s88-c-k-c0x00ffffff-no-rj"
				/>
			</router-link>
		</div>
	</header>
</template>

<script>
import { watch } from "vue";
import { useI18n } from "vue-i18n";

export default {
	name: "SiteHeader",
	// TODO: fix this scuffed code, cause it's reusing code from main.js?
	setup() {
		const { locale, t } = useI18n({
			useScope: "global",
		});
		watch(locale, (newVal) => {
			sessionStorage.setItem("locale", newVal);
		});
		return { locale, t };
	},
};
</script>

<style scoped>
header {
	position: sticky;
	top: 0;
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	padding: 0.5rem 1rem;
	background-color: #fff;
	z-index: 1;
}

a {
	width: max-content;
}

.nav-logo {
	height: 2rem;
	justify-self: left;
}

.nav-icons {
	display: flex;
	justify-content: center;
	align-items: center;
}

select {
	font-family: "Manrope", sans-serif;
	font-weight: bold;
	color: #5c5c5c;
	padding: 0.25rem 0.5rem;
	border: 2px solid #5c5c5c;
	border-radius: 0.25rem;
}

.profile-img {
	height: 2.5rem;
	border-radius: 50%;
	margin-left: 2rem;
}

.icon {
	margin-left: 1.5rem;
}

.nav-icons a {
	font-weight: bold;
	color: #444;
	text-decoration: none;
}

@media screen and (min-width: 960px) {
	header {
		padding: 0.5rem 2rem;
	}
}

@media screen and (min-width: 1200px) {
	header {
		padding: 0.5rem 3rem;
	}
}
</style>
