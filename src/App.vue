<template>
  <div class="flex justify-center text-[10px] text-blue-600">
    <div class="min-w-[793px] max-w-[793px] h-[1120px] overflow-hidden">
      <div class="p-6 h-full">
        <section class="styled p-1 h-full">
          <div class="list border-2 rounded border-blue-600 h-full p-2">
            <h1 class="text-center text-xl font-bold mb-[100px]">Title</h1>
            <div class="grid grid-cols-2 gap-20 mb-8">
              <div class="flex gap-2">
                <label for="name" class="text-base font-bold">பெயர்</label>
                <input type="text"
                  class="w-full h-full border-b-2 border-dotted border-blue-600 focus:outline-none text-center text-sm text-black">
              </div>
              <div class="flex gap-2">
                <label for="name" class="text-base font-bold">நாள்</label>
                <input type="text"
                  class="w-full h-full border-b-2 border-dotted border-blue-600 focus:outline-none text-center text-sm text-black">
              </div>
            </div>
            <div class="flex justify-center">
              <div class="bg-blue-600 text-white px-3 py-1 mb-2 text-sm rounded font-bold"> காய்கறி சிட்டை</div>
            </div>
            <div
              class="grid grid-cols-[1fr_50px_50px_1fr_50px_50px] border-2 border-blue-600 divide-x-2 divide-blue-600 h-6">
              <div class="h-full flex items-center px-3 font-bold"></div>
              <div class="h-full flex items-center justify-center font-bold w-full">
                கிலோ
              </div>
              <div class="h-full flex items-center justify-center font-bold w-full">
                கிராம்
              </div>
              <div class="h-full flex items-center px-3 font-bold"></div>
              <div class="h-full flex items-center justify-center font-bold w-full">
                கிலோ
              </div>
              <div class="h-full flex items-center justify-center font-bold w-full">
                கிராம்
              </div>
            </div>
            <div
              class="grid grid-cols-[1fr_50px_50px_1fr_50px_50px] border-2 border-blue-600 divide-x-2 divide-blue-600 h-6"
              v-for="(item, i) in  vegList " :key="i">
              <div class="h-full flex items-center px-3 font-bold">{{ item[0] }}</div>
              <div class="h-full flex items-center">
                <input type="text" class="w-full h-full focus:outline-none text-center text-sm text-black" />
              </div>
              <div class="h-full flex items-center">
                <input type="text" class="w-full h-full focus:outline-none text-center text-sm text-black" />
              </div>
              <div class="h-full flex items-center px-3 font-bold">{{ item[1] }}</div>
              <div class="h-full flex items-center">
                <input type="text" class="w-full h-full focus:outline-none text-center text-sm text-black" />
              </div>
              <div class="h-full flex items-center">
                <input type="text" class="w-full h-full focus:outline-none text-center text-sm text-black" />
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import List from "./vegetables.json";

const vegList = ref([]);

onMounted(() => {
  for (let i = 0; i < List.length; i += 2) {
    vegList.value.push(List.slice(i, i + 2));
  }
  document.addEventListener("keydown", function (event) {
    if ((event.ctrlKey || event.metaKey) && event.key === "s") {
      event.preventDefault();
      window.print();
    }
  });
});
</script>
<style scoped>
.styled {
  border: 1rem solid #2563eb;
  border-image: repeating-linear-gradient(45deg,
      transparent,
      transparent 5px,
      #2563eb 6px,
      #2563eb 15px,
      transparent 16px,
      transparent 20px) 20/1rem;
}

.list div:not(:last-child) {
  border-bottom: 0px;
}
</style>
