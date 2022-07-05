<script>
  import { onMount } from "svelte";

  /**
   * @type {HTMLIFrameElement}
   */
  let component;

  let isLogin = false;

  onMount(() => {
    console.log("hola", component);
  });
</script>

<iframe
  bind:this={component}
  src="https://final-login.vercel.app/"
  title={undefined}
/>

<h1>PET</h1>
<code>{isLogin}</code>
