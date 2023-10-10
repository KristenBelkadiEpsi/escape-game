<template>
  <BackToHomeButton />
    <div class="container-fluid">
        <h1>Salle de reunion</h1>
    </div>
</template>
<script>
import BackToHomeButton from '@/components/BackToHomeButton.vue';
export default {
  name: 'MeetingRoomView',
  components: {
        BackToHomeButton
    },
}
</script>