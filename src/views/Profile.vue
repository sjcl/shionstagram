<template>
	<main>
		<Menu />
		<section class="profile">
			<section class="profile-card">
				<img
					class="avatar-img"
					:alt="alt"
					src="../assets/images/messageHistory/shion.jpg"
				/>
				<div class="profile-body">
					<h2>{{ name }}</h2>
					<ul class="profile-stats">
						<li>
							{{ $t("profile.posts") }}
						</li>
						<li>
							{{ $t("profile.followers") }}
						</li>
						<li>
							{{ $t("profile.following") }}
						</li>
					</ul>
					<p class="description">{{ $t("profile.bio") }}</p>
					<div class="profile-socials">
						<a
							href="https://www.youtube.com/channel/UCXTpFs_3PqI41qX2d9tL2Rw"
							target="_blank"
							rel="noopener noreferrer"
							><img src="../assets/icons/YouTube.png" alt=""
						/></a>
						<a
							href="https://twitter.com/murasakishionch"
							target="_blank"
							rel="noopener noreferrer"
							><img src="../assets/icons/Twitter.png" alt=""
						/></a>
					</div>
				</div>
			</section>
			<hr />
			<section class="clip">
				<iframe
					src="https://www.youtube-nocookie.com/embed/AjbkMNO-JVQ"
					title="YouTube video player"
					frameborder="0"
					class="clip-embed"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
				></iframe>
				<div class="clip-desc">
					<p>
						{{ $t("profile.clip_description") }}
					</p>
				</div>
			</section>
			<hr />
			<section class="credits">
				<h3>Credits</h3>
				<div class="credits-body">
					<div class="credits-col">
						<h4>{{ $t("profile.artists") }}</h4>
						<ul>
							<li :key="artist" v-for="artist in credits.artists">
								{{ artist.name }}
								<a
									v-if="artist.twitter"
									:href="`https://twitter.com/${artist.twitter}`"
									>(@{{ artist.twitter }})</a
								>
							</li>
						</ul>
					</div>
					<div class="credits-col">
						<h4>{{ $t("profile.assistants") }}</h4>
						<ul>
							<li :key="assistant" v-for="assistant in credits.assistants">
								{{ assistant.name }}
								<a
									v-if="assistant.twitter"
									:href="`https://twitter.com/${assistant.twitter}`"
									>(@{{ assistant.twitter }})</a
								>
							</li>
						</ul>
					</div>
					<div class="credits-col">
						<h4>{{ $t("profile.leads") }}</h4>
						<ul>
							<li :key="lead" v-for="lead in credits.leads">
								{{ lead.name }}
								<a
									v-if="lead.twitter"
									:href="`https://twitter.com/${lead.twitter}`"
									>(@{{ lead.twitter }})</a
								>
							</li>
						</ul>
					</div>

					<div class="credits-col">
						<h4>{{ $t("profile.developers") }}</h4>
						<ul>
							<li :key="developer" v-for="developer in credits.developers">
								{{ developer.name }}
								<a
									v-if="developer.twitter"
									:href="`https://twitter.com/${developer.twitter}`"
									>(@{{ developer.twitter }})</a
								>
							</li>
						</ul>
					</div>
				</div>
			</section>
		</section>
	</main>
</template>

<script>
import Menu from "../components/Menu.vue";

export default {
	name: "Profile",
	components: {
		Menu,
	},
	data: () => ({
		name: "murasakishionch",
		posts: 0,
		followers: "1M",
		following: 0,
		credits: {
			artists: [
				{
					name: "シーナ",
					twitter: "Shiina__S",
				},
				{
					name: "侑",
					twitter: "oisiimizu_3",
				},
				{
					name: "たむろ",
					twitter: "tam_0315",
				},
				{
					name: "おうどん",
					twitter: "udonnaiyo",
				},
				{
					name: "ねこた",
					twitter: "Nekotaririn_EX",
				},
				{
					name: "しおこねこ",
					twitter: "ShiokkoNekko",
				},
				{
					name: "とりぷる/Tripl3",
					twitter: "toripuru_3",
				},
				{
					name: "100トン",
					twitter: "100ton250",
				},
				{
					name: "icicca",
					twitter: "aaln_1",
				},
				{
					name: "nanaco",
					twitter: "nanaco_41n",
				},
				{
					name: "ぽこぽこ",
					twitter: "pocopocoing",
				},
			],
			developers: [
				{
					name: "Cen",
				},
				{
					name: "matthew tao",
				},
				{
					name: "べべ",
					twitter: "sj67899745",
				},
				{
					name: "Rice-sama",
				},
			],
			leads: [
				{
					name: "BananaKyun",
					twitter: "Real_Bananakyun",
				},
				{
					name: "Coral Reef",
					twitter: "comfy_broom",
				},
				{
					name: "シーナ",
					twitter: "Shiina__S",
				},
			],
			assistants: [
				{
					name: "Neil",
				},
				{
					name: "Ao-Tan",
					twitter: "Ao_Tilt",
				},
				{
					name: "Ser",
				},
				{
					name: "Sunny・サニー",
					twitter: "Tsunnyrise",
				},
				{
					name: "Kusogaclips",
					twitter: "kusogaclips",
				},
				{
					name: "Mileina",
					twitter: "_Mileina",
				},
				{
					name: "りんたろ",
					twitter: "shion_kirinuki",
				},
				{
					name: "MAESH1M4",
					twitter: "Shionsukiiimask",
				},
			],
		},
	}),
};
</script>

<style scoped>
main {
	display: grid;
	width: 100%;
	margin: auto;
	padding: 3rem 1rem;
	gap: 2rem;
}

@media screen and (min-width: 650px) {
	main {
		grid-template-columns: max-content 1fr;
	}
}

@media screen and (min-width: 768px) {
	main {
		gap: 2rem;
		padding: 3rem 2rem;
	}
}
@media screen and (min-width: 1440px) {
	main {
		padding: 3rem;
	}
}

.profile {
	display: flex;
	flex-direction: column;
	align-items: center;
	gap: 4rem;
	margin: 0 auto;
	width: 100%;
	max-width: 55rem;
	color: var(--purple-200);
}

.profile-card {
	display: flex;
	justify-content: center;
	flex-wrap: wrap;
	gap: 2rem;
	color: var(--purple-400);
	background: hsla(292, 30%, 80%, 0.2);
	backdrop-filter: blur(6px);
	border: 1px solid white;
	padding: 2rem;
	border-radius: 0.5rem;
}

.avatar-img {
	flex-shrink: 0;
	height: 8rem;
	width: 8rem;
	border-radius: 50%;
	margin-top: 1rem;
}

.profile-body {
	display: flex;
	max-width: 60ch;
	flex-direction: column;
	padding: 0;
	white-space: pre-line;
}

.profile-body ul {
	display: flex;
	list-style: none;
	margin-bottom: 1.5rem;
}

.profile-body li {
	margin-right: 2.5rem;
}

.profile-body li span {
	font-weight: bold;
}

.profile-socials {
	margin-top: 1rem;
	display: flex;
	flex-direction: row;
	gap: 1rem;
}

.profile-socials img {
	height: 2.5rem;
	width: 2.5rem;
	object-fit: contain;
}

.clip {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	width: 100%;
	gap: 2rem;
}

.clip-embed {
	aspect-ratio: 16 / 9;
	height: 100%;
	width: 100%;
}

.clip-desc {
	width: 100%;

	padding: 2rem 1rem;
	background: hsla(292, 30%, 80%, 0.7);
	border: 1px solid white;
	border-radius: 0.5rem;
}

.clip p {
	max-width: 70ch;
	margin: auto;
}

.credits {
	display: flex;
	flex-direction: column;
	width: 100%;
	background: hsla(292, 30%, 80%, 0.7);
	border: 1px solid white;
	border-radius: 0.5rem;
	text-align: center;
}

.credits h3 {
	padding: 1rem;
	border-bottom: white 1px solid;
}

.credits-body {
	padding: 1.5rem 1rem;
	display: grid;
	grid-template-columns: 1fr;
	gap: 2rem;
}

@media screen and (min-width: 800px) {
	.credits-body {
		grid-template-columns: 1fr 1fr;
	}
}

.credits-col {
	display: flex;
	flex-direction: column;
	gap: 0.5rem;
}

.credits ul {
	list-style: none;
	padding: 0;
	line-height: 1.8;
}

.credits a {
	color: hsl(197, 30%, 40%);
	font-style: italic;
	text-decoration: none;
	font-size: 0.9rem;
}

hr {
	width: 100%;
	border: 0;
	height: 2px;
	background-color: var(--purple-500);
	border-radius: 999px;
}

h2 {
	font-size: 2rem;
	font-weight: 500;
	margin-bottom: 1.5rem;
}

button {
	font-size: 14px;
	line-height: 18px;
	appearance: none;
	padding: 5px 9px;
	background: 0 0;
	border-radius: 4px;
	margin: 0;
}
</style>
