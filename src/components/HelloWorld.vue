<template>
  <div class="feedback-btn">
    <button class="btn btn-info" @click="showModal(true)">send feedback</button>
    <UserFeedback class="feedback-modal" :class="{ 'show-modal': modelType }" @close-modal="onCloseModal"></UserFeedback>
    <!-- Success Modal -->
    <div v-if="showSuccessModal" class="success-modal card">
      <div class="card-body">
        <p class="fs-2 text-success">提交成功</p>
        <a href="" class="close-btn" @click="closeSuccessModal(false)">X</a>
        <p>感謝您的反饋，我們將會繼續努力，提供更優質的服務！</p>
      </div>
    </div>
  </div>
</template>

<script>
import UserFeedback from './UserFeedback.vue';

export default {
  name: 'HelloWorld',
  components: {
    UserFeedback,
  },
  data() {
    return {
      modelType: false,
      showSuccessModal: false,
    }
  },
  methods: {
    showModal(status) {
      this.modelType = status;  // Toggle the model state between true and false.
    },
    onCloseModal(state) {
      this.showSuccessModal = true;

      setTimeout(() => {
        this.showSuccessModal = false;
        this.modelType = state;  // Close the modal when the close button is clicked.
      }, 5000);
    },
    closeSuccessModal(state) {
      this.showSuccessModal = false;
      this.modelType = state;
    },
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.feedback-btn {
  margin-bottom: 20px;
}

.feedback-modal {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}

.show-modal {
  display: block;
}

.success-modal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  padding: 20px;
  border: 1px solid #000;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  z-index: 1000;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 24px;
  cursor: pointer;
  color: #000;
}
</style>