<script>
	let url = "";
	let stats = "";
	let id = "";
	async function newlink() {
		stats = "please wait ...";
		if(url != ""){
			const res = await fetch('https://api.johnling1.repl.co/add?db=url&data={"url":"'+url+'"}');
			id = await res.text();
			stats = "https://domain/"+id;
		}else{
			stats = "Url Should not be Empty !";
		}
	}
</script>

<main>
	<h1>Shorten It</h1>
	<input bind:value={url}>
	<button on:click={newlink}>Shorten The Url</button>
	<p>{stats}</p>
</main>

<style>

</style>