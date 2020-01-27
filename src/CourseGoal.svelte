<script>
	export let goal;

	$: hasExclaimation = goal.includes("!");
</script>

<style>
	.accent {
		color: red;
	} 
</style>

<h1 class:accent={hasExclaimation}>{goal}</h1>