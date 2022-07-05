<script>
  import { onMount } from "svelte";

  /**
   * @type {HTMLIFrameElement}
   */
  let component;

  let isLogin = false;

  let value;
  onMount(() => {
    component.contentWindow.addEventListener("message", (e) => {
      console.log("ni idea pa que sirve esta madre", e);
    });
  });
  const handleClick = () => {
    component.contentWindow.postMessage(
      value,
      "https://final-login.vercel.app"
    );
  };
</script>

<iframe
  bind:this={component}
  src="https://final-login.vercel.app"
  title={undefined}
/>

<h1>PET</h1>

<input bind:value />

<button on:click={handleClick}>send message</button>
<code>{isLogin}</code>
