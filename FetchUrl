<script>
	let url = 'https://dummyjson.com/products/search?q=Laptop'
  let data = null;
	let selectedOption = 'products'; 
	const options = [
    'products',
    'categories',
    'search'
  ];

	function handleChange(event) {
    selectedOption = event.target.value;
		if(selectedOption === "products"){
			url = "https://dummyjson.com/products"
		}

		if(selectedOption === "categories"){
			url = "https://dummyjson.com/products/categories"
		}

		if(selectedOption === "search"){
			url = "https://dummyjson.com/products/search?q=Laptop"
		}
  }

  async function fetchData() {
    try {
      const response = await fetch(url); // Replace with your URL
      if (response.ok) {
        data = await response.json();
      } else {
        console.error('Error fetching data:', response.status,response.statusText);
      }
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  }
</script>


<div class="form-container">
<form on:submit|preventDefault={fetchData}>
    <div class="form-group">
			<label for="dropdown">Select an option:</label>
			<select bind:value={selectedOption} on:change={handleChange}>
			  {#each options as option}
			    <option value={option}>{option}</option>
			  {/each}
</select>
			    <div class="form-group">
      <label for="inputString">URL:</label>
			<input id="inputString"  size="80" type="text" bind:value={url} placeholder="Enter URL" />			
    </div>
		</div>
	<!-- <button on:click={fetchData} type="submit">Submit</button> -->
	<button type="submit">
		Submit
	</button>
</form>
{#if data}
  <pre>{JSON.stringify(data, null, 2)}</pre>
{/if}
</div>

<!-- Style -->
<style>
  .form-container {
    display: flex;
    flex-direction: column;
    width: 300px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  .form-group {
    margin-bottom: 10px;
  }

  label {
    font-weight: bold;
    margin-bottom: 5px;
  }

  select,
  input {
    width: 100%;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  button {
    padding: 10px 15px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  button:hover {
    background-color: #0056b3;
  }
</style>

