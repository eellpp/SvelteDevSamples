<script>
	let title = 'This is a example post';
	let user = 'johndoe';
	let userId = 2;
	let result = '';
	
	async function doPost () {
		let postData = JSON.stringify({
				title,
				userId,
				user
			});
		console.log(postData);
		const res = await fetch('https://dummyjson.com/posts/add', {
			method: 'POST',
			headers: { 'Content-Type': 'application/json' },
			  body: postData
		});
		
		const json = await res.json()
		result = JSON.stringify(json)
	}
</script>


<input bind:value={title} />
<input bind:value={user} />
<input bind:value={userId} />
<button type="button" on:click|preventDefault={doPost}>
	Post it.
</button>
<p>
	Result:
</p>
<pre>
{result}
</pre>
