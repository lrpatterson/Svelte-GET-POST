<script>
// {
//     "id": 2,
//     "description": "Sweet and savory sauces relishes spreads and seasonings",
//     "name": "Condiments"
//   },

var content = JSON.stringify({
    "id": 2,
    "description": "Sweet and savory sauces relishes spreads and seasonings",
    "name": "Condiments"
  })
const options = {
  method: 'POST',
  body: JSON.stringify(content),
  headers: {
    'Content-Type': 'application/json'
  }
};
function createCategory(opts) {
  
  fetch('https://www.northwind.now.sh/api/categories', options)
  .then(res => res.json())
  .then(res => console.log(res));
}


function submitCategory() {
  
  createCategory(content);
  
}



</script>

<textarea bind:value={content}></textarea>
<button on:click={submitCategory}>Submit Category
</button>