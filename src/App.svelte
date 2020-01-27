<script>
	import ContactCard from './ContactCard.svelte';

	let name = "Andrew";
	let age = 30;
	let jobTitle = "Programmer";
	let description = "Description goes here";
	let imgSrc="";

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

	const nameInput = event => name = event.target.value;

</script>

<style>
	h1 {
		color: purple;
	}

	.description-wrapper {
		margin-top: 15px;
	}
</style>

<h1>Hello {uppercaseName}! My age is {age}</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" value={name} on:input={nameInput}> -->
<input type="text" bind:value={name}>
<input type="text" bind:value={jobTitle}>
<label for="imgSrc">Image Src:</label>
<input type="text" id="imgSrc" bind:value={imgSrc}>
<div class="description-wrapper">
	<textarea name="description" bind:value={description} rows="3"></textarea>
</div>

<ContactCard
	userName={name}
	{jobTitle}
	{description}
	imgSrc={imgSrc}
/>

