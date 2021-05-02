<template>
	<select
		v-model="selected"
		class="block mt-2 border rounded w-auto md:mx-40 mx-16 p-2 mb-12"
	>
		<option value="0">Select Country</option>
		<option v-for="country in countries" :key="country.ID">{{
			country.Slug
		}}</option>
	</select>
</template>

<script>
	export default {
		name: "CountrySelect",
		props: ["countries"],
		data() {
			return {
				selected: 0,
			};
		},
	};
</script>
