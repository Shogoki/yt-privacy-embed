<script lang="ts">
	/* Based on Light YouTube Embeds by @labnol */
	/* Web: https://www.labnol.org/ */
	import { onMount, tick } from 'svelte'; 
	
	export let videoid: string = "AdNJ3fydeao";
	export let thumbnail: string; //= `https://i.ytimg.com/vi/${videoid}/hqdefault.jpg`; // Defaulting to fetch it from yt
	export let embedoptions: string = "autoplay=1&rel=0"
	export let title: string = "Video"
	export let width = "400"
	export let height = "200"
  export let overlaytext: string;
	let enabled = false;

	onMount(async () => {
		await tick();
		thumbnail = thumbnail ?? `https://i.ytimg.com/vi/${videoid}/hqdefault.jpg`
  });

</script>
<svelte:options tag="privacy-yt-embed"></svelte:options>

<div class="youtube-player" style="width:{width}{isNaN(width) ? "" : "px"}; height: {height}{isNaN(height) ? "" : "px"};" >
	{#if enabled}
	<iframe  title="{title}" src={`https://www.youtube-nocookie.com/embed/${videoid}?${embedoptions}`} frameborder="0" allowfullscreen="1" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" ></iframe>
	{:else}
	<div>
		<img src={thumbnail} alt="thumbnail for Video" />
		<div class="play" on:click={() => enabled = true}></div>
    {#if overlaytext}
      <div class="privacy">{overlaytext}</div>
    {/if}
	</div>
	{/if}
</div>	







<style>


.youtube-player {
  position: relative;
  height: 0;
  overflow: hidden;
  max-width: 100%;
  background: #000;
  margin: 5px;
}

.youtube-player iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 100;
  background: transparent;
}

.youtube-player img {
  object-fit: cover;
  display: block;
  left: 0;
  bottom: 0;
  margin: auto;
  max-width: 100%;
  width: 100%;
  position: absolute;
  right: 0;
  top: 0;
  border: none;
  height: auto;
  cursor: pointer;
  -webkit-transition: 0.4s all;
  -moz-transition: 0.4s all;
  transition: 0.4s all;
}

.youtube-player img:hover {
  -webkit-filter: brightness(75%);
  -moz-filter: brightness(75%);
  filter: brightness(75%);
}

.youtube-player .play {
  height: 72px;
  width: 72px;
  left: 50%;
  top: 50%;
  margin-left: -36px;
  margin-top: -36px;
  position: absolute;
  background-image: url("data:image/png;base64,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");
  cursor: pointer;
}

.youtube-player .privacy {
    --text-color: white;
    color: var(--text-color);
    position: absolute;
    top: calc(50% + 36px);
    text-align: center;
    width: 100%;

}

</style>