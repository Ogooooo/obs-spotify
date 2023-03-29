<script>
	import { useLanyard } from "svelte-lanyard";
	const data = useLanyard("420661585007083520", { type: 'rest', restInterval: 1e3 });
</script>

<main class="container">
  {#if $data && $data.listening_to_spotify}
  <div class="box">
    <img src={$data.spotify.album_art_url}  alt="logo">
    <div class="text">
      <p>Listening to {$data.spotify.song} <br> by {$data.spotify.artist}</p>
    </div>
  </div>
{:else}
  <!-- Loads faster with this dunno why -->
{/if}
</main>

<style lang="scss">
@import url("https://api.fontshare.com/v2/css?f[]=satoshi@1,900,700,500,301,701,300,501,401,901,400,2&display=swap");

:global(*) {
  font-family: "Satoshi";
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  color: #f1f5f9;
}

.box {
  display: flex;
  padding: 1rem;
  min-width: 19rem;
  max-width: max-content;
  background: rgba(0, 0, 0, 0.500);
  border-radius: .4rem;
  font-size: 1.1rem;
  font-weight: 600;
}

img {
  position: relative;
  height: 5rem;
  border-radius: .4rem;
}

.text {
  margin: auto 1rem; 
}
</style>
