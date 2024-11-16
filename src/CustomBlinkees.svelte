<script>
  let uploadedImage = null;
  let leds = [];
  let dragColor = '';
  let currentLEDIndex = -1;
  let animationInterval = null;
  let fileInput;

  // Handle image file upload
  function fileUpload(event) {
    const file = event.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = (e) => {
        uploadedImage = e.target.result;
      };
      reader.readAsDataURL(file);
    }
  }

  // Handle drag start for LEDs
  function handleDragStart(event, color) {
    dragColor = color;
  }

  // Handle drop event for placing LEDs
  function handleDrop(event) {
    event.preventDefault();
    const rect = event.target.getBoundingClientRect();
    const x = event.clientX - rect.left - 15;
    const y = event.clientY - rect.top - 15;
    leds = [...leds, { x, y, color: dragColor, effect: '' }];
  }

  function handleDragOver(event) {
    event.preventDefault();
  }

  // Function to animate LEDs with specific effect
  function animateLEDs(effect) {
    if (leds.length === 0) return;
    stopAnimations(); // Stop any ongoing animation

    let index = 0;

    animationInterval = setInterval(() => {
      // Apply effect to one LED at a time
      leds = leds.map((led, i) => ({
        ...led,
        effect: i === index ? effect : 'hidden'
      }));

      // Move to the next LED in sequence
      index = (index + 1) % leds.length;
    }, effect === 'flash' ? 700 : 2000); // Longer interval for flash, equal fade timing
  }

  // Stop all animations
  function stopAnimations() {
    clearInterval(animationInterval);
    animationInterval = null;
    leds = leds.map(led => ({ ...led, effect: '' }));
  }

  // Reset everything
  function resetUpload() {
    stopAnimations();
    uploadedImage = null;
    leds = [];

    if (fileInput) {
      fileInput.value = '';
    }
  }
</script>

<div class="blinky-builder">
  <h1>Blinky Builder</h1>

  <div class="upload-section">
    <label for="upload">Upload Your Artwork:</label>
    <input type="file" id="upload" accept="image/*" bind:this={fileInput} on:change={fileUpload} />
  </div>

  {#if uploadedImage}
    <div
      id="image-container"
      class="uploaded-image"
      on:dragover={handleDragOver}
      on:drop={handleDrop}
    >
      <img id="uploaded-image" src={uploadedImage} alt="Uploaded Artwork" />

      {#each leds as { x, y, color, effect }}
        <div
          class="led dropped"
          style="left: {x}px; top: {y}px; background-color: {color};"
          class:flash={effect === 'flash'}
          class:fade={effect === 'fade'}
          class:hidden={effect === 'hidden'}
        ></div>
      {/each}
    </div>
  {/if}

  <div class="leds">
    {#each ['red', 'orange', 'yellow', 'green', 'blue', 'purple', 'pink', 'white'] as color}
      <div
        class="led"
        draggable="true"
        on:dragstart={(e) => handleDragStart(e, color)}
        style="background-color: {color};"
      ></div>
    {/each}
  </div>

  <div class="buttons">
    <button class="styled-button" on:click={() => animateLEDs('flash')}>Make it Flash</button>
    <button class="styled-button" on:click={() => animateLEDs('fade')}>Make it Fade</button>
    <button class="styled-button" on:click={stopAnimations}>Stop Animations</button>
    <button class="styled-button" on:click={resetUpload}>Reset</button>
  </div>
</div>

<style>
  .blinky-builder {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }

  #image-container {
    position: relative;
    display: inline-block;
    margin: 20px auto;
  }

  #uploaded-image {
    display: block;
    max-width: 100%;
    max-height: 80vh;
    object-fit: contain;
  }

  .led {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    cursor: pointer;
  }

  .dropped {
    position: absolute;
  }

  @keyframes fade {
    0%, 100% {
        opacity: 0;
    }
    50% {
        opacity: 1;
    }
}

.fade {
    animation: fade 2s linear forwards;
}

  .hidden {
    display: none;
  }

  .leds {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-top: 10px;
  }

  .buttons {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
  }

  .styled-button {
    background-color: #ff00c8;
    color: #000;
    border: none;
    border-radius: 20px;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
</style>
