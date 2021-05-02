<template>
	<main
		class="flex flex-col align-center justify-center text-center text-items-center"
		v-if="!loading"
	>
		<div class="text-gray-600 text-2xl mt-10 mb-6">
			<DataTitle :text="title" :dataDate="dataDate" />
			<DataBoxes :stats="stats" />
		</div>

		<CountrySelect :countries="countries" />
	</main>

	<main class="flex flex-col align-center justify-center text-center" v-else>
		<div class="text-gray-400 text-2xl mt-10 mb-6">
			Fetching Data
		</div>
		<img :src="loadingImage" class="w-16 m-auto" alt="" />
	</main>
</template>

<script>
	import DataTitle from "@/components/DataTitle";
	import DataBoxes from "@/components/DataBoxes";
	import CountrySelect from "@/components/CountrySelect";

	// @ is an alias to /src
	export default {
		name: "Home",
		components: {
			DataTitle,
			DataBoxes,
			CountrySelect,
		},
		data() {
			return {
				loading: true,
				title: "Global",
				dataDate: "",
				stats: {},
				countries: [],
				loadingImage: require("../assets/Spinner-1s-200px.svg"),
			};
		},
		methods: {
			async fetchCovid() {
				const result = await fetch("https://api.covid19api.com/summary");
				const data = await result.json();
				return data;
			},
		},
		async created() {
			const data = await this.fetchCovid();

			this.dataDate = data.Date;
			this.stats = data.Global;
			this.countries = data.Countries;
			this.loading = false;
		},
	};
</script>
