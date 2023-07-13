<script>
    import { t, locale, locales } from "../../resources/locale/i18n";

    $: time = new Date().toLocaleDateString($locale, {
        weekday: "long",
        year: "numeric",
        month: "long",
        day: "numeric",
    });
</script>

<img src="/images/farindra.jpg" alt="Image" />
<h1>{$t("homepage.title")}!</h1>
<p>{@html $t("homepage.welcome", { name: "Jane Doe" })}!</p>
<p>{@html $t("homepage.time", { time })}!</p>
<select bind:value={$locale}>
    {#each locales as l}
      <option value={l}>{l}</option>
    {/each}
  </select>

<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
