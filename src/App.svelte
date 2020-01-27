<script>
	let name = "Andrew";
	let age = 30;

	$: uppercaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === "A different name"){
		age = 105;
	}

	const incrementAge = () => {
		age += 1;
	};

	const changeName = () => {
		name = "A different name"
	}

	const nameInput = event => {
		name = event.target.value;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}! My age is {age}</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" value={name} on:input={nameInput}> -->
<input type="text" bind:value={name}>

