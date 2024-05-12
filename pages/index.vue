<template>
  <div class="">
    <header class="absolute inset-x-0 bottom-0 w-full">
      <div class="grid grid-flow-col gap-1 justify-stretch w-full h-full">
        <button
          class="bg-gray-300 text-blue-900 p-3"
          v-for="btn in bottomSheetButtons"
        >
          <div class="flex justify-center gap-2 items-center">
            <img class="w-8 h-8" :src="btn.icon" />
            {{ btn.label }}
          </div>
        </button>
      </div>
    </header>
    <button
      class="m-4 p-4 rounded bg-green-400 hover:ring"
      @click="dialog?.showModal()"
    >
      Mostrar pop-up
    </button>
    <dialog ref="dialog" class="p-8 backdrop:bg-black/40 w-48">
      <p>Vídeo</p>
      <button
        class="m-4 p-4 rounded bg-green-400 hover:ring float-end"
        @click="dialog?.close()"
      >
        OK
      </button>
    </dialog>
  </div>
</template>

<script setup lang="ts">
const bottomSheetButtons = [
  { label: "Lista", icon: "/_tela01/Icon Lista.svg" },
  { label: "Mapa", icon: "/_tela01/Icon Mapa.svg" },
  { label: "Suporte", icon: "/_tela01/Fones.svg" },
  { label: "Ajustes", icon: "/_tela01/Engrenagem.svg" },
];

const dialog = ref<HTMLDialogElement>();
</script>
