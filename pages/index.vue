<template>
  <div class="">
    <header id="bottom-nav" class="absolute inset-x-0 bottom-0 w-full z-50">
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
    <div id="content" class="flex flex-col-reverse h-svh min-h-svh">
      <div id="main" class="basis-2/3 shrink-0 -mt-8 bg-white rounded-t-3xl">
        <button
          class="m-4 p-4 rounded bg-green-400 hover:ring z-30"
          @click="dialog?.showModal()"
        >
          Mostrar pop-up
        </button>
      </div>
      <div id="background" class="basis-1/3">
        <img
          src="/_tela01/close-up.png"
          class="object-cover h-full w-svw z-10"
        />
        <button>
          <img src="/_tela01/Bt_X.svg" class="absolute top-0 end-0 m-4 z-20" />
        </button>
      </div>
    </div>

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
  { label: "Lista", icon: "/_tela01/IconLista.svg" },
  { label: "Mapa", icon: "/_tela01/IconMapa.svg" },
  { label: "Suporte", icon: "/_tela01/Fones.svg" },
  { label: "Ajustes", icon: "/_tela01/Engrenagem.svg" },
];

const dialog = ref<HTMLDialogElement>();
</script>
