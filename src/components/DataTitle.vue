<template>
	<div class="text-center">
		<h2 class="text-3xl font-bold">{{ text }}</h2>
		<div class="text-2xl mt-2 mb-8">
			{{ timestamp }}
		</div>
	</div>
</template>

<script>
	import moment from "moment";

	export default {
		name: "DataTitle",
		props: ["text", "dataDate"],
		computed: {
			timestamp: function() {
				return moment(this.dataDate).format("D MMMM YYYY, h:mm:ss a");
			},
		},
	};
</script>
