<script>
  let showModal = false;
  let selectedButton = null;
  
  function openModal() {
    showModal = true;
  }
  
  function closeModal() {
    showModal = false;
  }
  
  function handleButtonClick(button) {
    selectedButton = button;
    closeModal();
  }
  
  function handleButtonKeyDown(event) {
    if (event.key === 'Enter' || event.key === ' ') {
      openModal();
    }
  }
</script>

<button class="green-button" on:click={openModal} on:keydown={handleButtonKeyDown} tabindex="0"><h3>?</h3></button>

{#if showModal}
  <div class="modal" on:click={closeModal} on:keydown={(event) => {if (event.key === 'Escape') closeModal()}}>
    <div class="modal-content" on:click={(e) => e.stopPropagation()}>
      <button class="close-button" on:click={closeModal}>X</button>
      <h2 class="choose-option-title">Choose an option:</h2>
      <button class="option-button" on:click={() => handleButtonClick('option1')}><h2>Mint Start bonus</h2></button>
      <button class="option-button" on:click={() => handleButtonClick('option2')}><h2>Mint End bonus</h2></button> <!-- Can add more buttons easily -->
    </div>
  </div>
{/if}

{#if selectedButton}
  <!-- <p>Selected option: {selectedButton}</p>
  Handle metamask queries here when pressing one of the buttons such as making a tx signal to da blockchain
  -->
{/if}

<style>
  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .modal-content {
    background-color: var(--black-blue);
    padding: 20px;
    border-radius: 5px;
    max-width: 500px;
  }

  .choose-option-title {
    margin-top: 4rem;
  }
  
  .close-button {
    background-color: #f44336;
    color: white;
    border: none;
    padding: 0.2rem;
    font-size: 1.5rem;
    border-radius: 4px;
    cursor: pointer;
    float: right;
  }
  
  .close-button:hover {
    opacity: 0.8;
  }
  
  .option-button {
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    margin-top: 10px;
  }
  
  .option-button:hover {
    opacity: 0.8;
  }
  
  .green-button {
    background-color: #4CAF50;
    color: white;
    padding: 2px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .green-button:hover {
    opacity: 0.8;
  }
</style>