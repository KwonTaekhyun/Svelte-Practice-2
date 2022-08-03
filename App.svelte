<script>
  import One from "./One.svelte";
  import Two from "./Two.svelte";
  import Three from "./Three.svelte";

  const options = [
    { category: "one", component: One },
    { category: "two", component: Two },
    { category: "three", component: Three }
  ];

  let selected = options[0];
</script>

<main>
	<div>
    <select bind:value={selected}>
      { #each options as option }
        <option value={option}>{option.category}</option>
      { /each }
    </select>
	</div>
  <div>
    <svelte:component this={selected.component} />
  </div>
</main>