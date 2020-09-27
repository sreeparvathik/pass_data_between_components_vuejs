<template>
  <div>
    <!-- Trigger/Open The Modal -->
    <br />
    <!-- The Modal -->
    <div id="myModal" class="modal">
      <!-- Modal content -->
      <div class="modal-content">
        <span class="close">&times;</span>
        <p style="text-align: left; font-weight: bold">{{ headingMessage }}</p>
        <p>{{ confirmationMessage }}</p>
        <button
          class="confirmation-button red"
          @click="$emit('confirmation', 'yes')"
        >
          Yes
        </button>
        <button
          class="confirmation-button green"
          @click="$emit('confirmation', 'no')"
        >
          No
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    headingMessage: String,
    confirmationMessage: String,
  },
  mounted() {
    // Get the modal
    var modal = document.getElementById("myModal");

    // Get the button that opens the modal
    var parentBtn = document.getElementById("parent");

    // Get the <span> element that closes the modal
    var span = document.getElementsByClassName("close")[0];

    // When the user clicks the button, open the modal

    parentBtn.onclick = function () {
      modal.style.display = "block";
    };

    // When the user clicks on <span> (x), close the modal
    span.onclick = function () {
      modal.style.display = "none";
    };

    // When the user clicks anywhere outside of the modal, close it
    window.onclick = function (event) {
      if (event.target === modal) {
        modal.style.display = "none";
      }
    };
  },
};
</script>

<style scoped>
/* The Modal (background) */
.modal {
  display: none; /* Hidden by default */
  position: fixed; /* Stay in place */
  z-index: 1; /* Sit on top */
  left: 0;
  top: 0;
  width: 100%; /* Full width */
  height: 100%; /* Full height */
  overflow: auto; /* Enable scroll if needed */
  background-color: rgb(0, 0, 0); /* Fallback color */
  background-color: rgba(0, 0, 0, 0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
  background-color: #fefefe;
  margin: 15% auto; /* 15% from the top and centered */
  padding: 20px;
  border: 1px solid #888;
  width: 80%; /* Could be more or less, depending on screen size */
}

/* The Close Button */
.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
.confirmation-button {
  margin: 2px;
  border: none;
  padding: 5px;
  width: 40px;
}
.red {
  background-color: rgb(170, 28, 28);
  color: white;
}
.green {
  background-color: rgb(24, 97, 18);
  color: white;
}
</style>
