<script lang="ts">
  import Game from './Game.svelte';
  import '../styles.css';
  import Modal from './Modal.svelte';

  let state: 'waiting' | 'playing' | 'paused' | 'won' | 'lost' = 'waiting';
</script>

<Game />
{#if state !== 'playing'}
  <Modal>
    <header>
      <h1>e<span>match</span>i</h1>
      <p>the emoji matching game</p>
    </header>

    {#if state === 'won' || state === 'lost'}
      <p>you {state} the game!</p>
    {:else if state === 'paused'}
      <p>game paused</p>
    {:else if state === 'waiting'}
      <p>choose a level:</p>
    {/if}
  </Modal>
{/if}

<style>
  h1 {
    font-size: 4em;
  }
  h1 span {
    color: purple;
  }

  p {
    font-family: Grandstander;
  }
</style>
