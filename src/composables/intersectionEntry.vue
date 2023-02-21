<script>
import { ref } from "vue";
const useIntersectionEntry = () => {
  const observedElement = ref("");
  const elementClass = ref("");
  const interOptions = (rootPar, thresholdPar) => {
    return {
      root: rootPar,
      threshold: thresholdPar,
    };
  };
  const interCallback = function (entries) {
    if (entries) {
      const [entry] = entries;
      if (entry.isIntersecting) {
        for (const el of elementClass.value) {
          observedElement.value.classList.add(el);

        }
      }
    }
  };
  const observer = new IntersectionObserver(interCallback, interOptions);
  return {
    observedElement,
    elementClass,
    interOptions,
    interCallback,
    observer,
  };
};
export default useIntersectionEntry;
</script>