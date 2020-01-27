<script>
	let name = "Andrew";
	let age = 30;

	$: uppercaseName = name.toUpperCase();

	const incrementAge = () => {
		age += 1;
	};

	const changeName = () => {
		name = "A different name"
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}! My age is {age}</h1>
<button on:click={incrementAge}>Change Age</button>
<button on:click={changeName}>Change Name</button>
