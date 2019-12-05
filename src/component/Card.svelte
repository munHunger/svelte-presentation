<script>
  export let icon;
  export let bullets;
  export let color = "#F95738";
</script>

<style>
  .card {
    box-shadow: 0px 2px 5px 1px rgba(0, 0, 0, 0.25);
    padding: 15px;
    margin: 15px;
    min-width: 200px;
    min-height: 250px;
    position: relative;
    padding-top: 75px;
    padding-bottom: 50px;
  }
  .icon {
    position: absolute;
    left: 50%;
    top: 0px;
    transform: translate(-50%, -50%);
    background-color: #eee;
    width: 150px;
    height: 150px;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    display: inline-block;
    border-radius: 100%;
    box-shadow: 0px 2px 5px 1px rgba(0, 0, 0, 0.25);
  }
  .head {
    top: 10px;
  }
  .line {
    height: 15px;
    position: absolute;
    width: 100%;
    left: 0px;
  }

  .bullet {
    font-size: 1.75em;
    margin-bottom: 5px;
  }
</style>

<div class="card">
  <div class="head line" style="background-color: {color}" />
  <div class="icon" style="background-image: url('{icon}')" />
  <div class="content">
    {#each bullets as bullet}
      <div class="bullet">{bullet}</div>
    {/each}
  </div>
  <div class="foot line" style="background-color: {color}; bottom: 10px" />
  <div class="foot line" style="background-color: {color}; bottom: 30px;" />
</div>
