<script>
  import Card from "./Card.svelte";
  let page = 3;
</script>

<style>
  .content {
    position: absolute;
    left: 50%;
    top: 50%;
    width: fit-content;
    height: fit-content;
    transform: translate(-50%, -50%);
    font-family: "Roboto Mono", monospace;
    display: inline-flex;
  }
  .title {
    font-size: 4em;
    font-weight: 600;
    color: #aaa;
  }
  .flash {
    animation: flash-keyframes 3s ease-in infinite;
  }
  @keyframes flash-keyframes {
    0% {
      opacity: 0.6;
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0.6;
    }
  }

  .lower-logo {
    position: absolute;
    right: 5%;
    bottom: 5%;
    opacity: 0.5;
  }

  .icon {
    position: relative;
    width: 150px;
    height: 150px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    display: inline-block;
  }

  .fade-in {
    animation: fade-in-keyframes 1s ease-out forwards;
  }

  @keyframes fade-in-keyframes {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
</style>

<div class="lower-logo">
  <img src="img/logo.png" alt="company logo" style="width:200px" />
</div>

<div class="content">
  {#if page === 1}
    <div class="title flash">Press any key to begin...</div>
  {/if}
  {#if page === 2}
    <div class="fade-in">
      <div
        class="icon"
        style="background-image: url('img/framework/angular.png');" />
      <div
        class="icon"
        style="background-image: url('img/framework/backbone.png');" />
      <div
        class="icon"
        style="background-image: url('img/framework/ember.png');" />
      <div
        class="icon"
        style="background-image: url('img/framework/react.png');" />
      <div
        class="icon"
        style="background-image: url('img/framework/vue.png');" />
      <div
        class="icon"
        style="background-image: url('img/framework/jquery.png');" />
    </div>
  {/if}

  {#if page === 3}
    <div class="fade-in" style="display: inherit">
      <Card
        icon="img/framework/react.png"
        bullets={['redux', '193KB', 'virtual dom', 'lighthouse 80', 'framework']} />
      <Card
        icon="img/framework/angular.png"
        bullets={['noone knows', '149KB', 'virtual dom', 'lighthouse 93', 'framework']} />
      <Card
        icon="img/framework/vue.png"
        bullets={['vuex', '41KB', 'virtual dom', 'lighthouse 94', 'framework']} />
      <Card
        icon="img/framework/svelte.png"
        bullets={['writable store', '9KB', 'no virtual dom', 'lighthouse 91', 'not a framework']} />
    </div>
  {/if}
</div>
