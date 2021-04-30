<template>
	<div class="grid md:grid-cols-2 gap-4">
		<!--Box 1-->
		<div class="shadow-md bg-green-100 p-10 text-center rounded mx-6">
			<h3 class="text-3xl text-green-900 font-bold mb-6">Cases</h3>
			<div class="text-2xl mb-4">
				<span class="font-bold">New:</span>
				{{ stats.NewConfirmed }}
			</div>
			<div class="text-2xl mb-4">
				<span class="font-bold">Total:</span>
				{{ stats.TotalConfirmed }}
			</div>
		</div>
		<!--Box 2-->
		<div class="shadow-md bg-green-200 p-10 text-center rounded mx-6">
			<h3 class="text-3xl text-green-900 font-bold mb-6">Deaths</h3>
			<div class="text-2xl mb-4">
				<span class="font-bold">New:</span>
				{{ stats.NewDeaths }}
			</div>
			<div class="text-2xl mb-4">
				<span class="font-bold">Total:</span>
				{{ stats.TotalDeaths }}
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: "DataBoxes",
		props: ["stats"],
	};
</script>
