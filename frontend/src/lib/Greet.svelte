<script lang="ts">
  //import { Greet } from "../../wailsjs/go/main/App";
  import { Greet } from "$wailsjs/go/main/App"
  let msg: string = $state("")
  const increment = () => {
    Greet(new Date().toLocaleString()).then((result) => msg = result)
  }
</script>
  
  <button onclick={increment}>
    Greet is {msg}x
  </button>
  