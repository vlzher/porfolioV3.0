<script>
import {onUnmounted, ref} from "vue";
import {onMounted} from "@vue/runtime-core";
const useScrollDirection = () => {
  const direction = ref('up');
  const startY = ref(0);
  const handleScroll = () => {
    const currentY = window.scrollY;
    if (currentY > startY.value) {
      direction.value = "down";
    } else {
      direction.value = "up";
    }
    startY.value = currentY;
  };
  onMounted(() => {
    window.addEventListener("scroll", handleScroll);
  });
  onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
  });
  return  direction;
}
export default useScrollDirection;
</script>