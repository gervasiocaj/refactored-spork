<template>
  <div class="">
    <header id="bottom-nav" class="fixed inset-x-0 bottom-0 w-full z-50">
      <div class="grid grid-flow-col gap-1 justify-stretch w-full h-full">
        <button
          class="bg-gray-300 active:bg-gray-400 text-blue-900 p-3"
          v-for="btn in bottomSheetButtons"
        >
          <div class="flex justify-center gap-2 items-center">
            <img class="w-8 h-8" :src="btn.icon" />
            {{ btn.label }}
          </div>
        </button>
      </div>
    </header>
    <div id="content" class="flex flex-col-reverse">
      <div
        id="main"
        class="basis-2/3 relative top-[-100px] bg-white rounded-t-3xl z-30"
      >
        <p class="font-bold mt-8 text-4xl text-blue-800 mx-8">
          Como ficam meus benefícios?
        </p>
        <div
          class="grid grid-cols-2 gap-4 content-stretch mt-8 mx-8 lg:max-w-[600px]"
        >
          <button
            v-for="bnf in mainBenefits"
            class="border-2 active:bg-gray-100 border-blue-900/50 rounded-xl flex flex-col items-center justify-center gap-5 py-8 max-lg:landscape:py-4 max-lg:landscape:aspect-auto aspect-square"
            @click="dialog?.showModal()"
          >
            <img class="h-14" :src="bnf.icon" />
            <p class="text-3xl text-center text-gray-500">{{ bnf.label }}</p>
          </button>
        </div>
      </div>
      <div id="background" class="basis-1/4 bg-gray-700">
        <img
          src="/_tela01/close-up.png"
          class="z-10 object-cover mx-auto lg:max-h-[500px] max-lg:landscape:max-h-[250px]"
        />
        <button>
          <img
            src="/_tela01/Bt_X.svg"
            class="absolute top-0 end-0 m-4 h-10 w-10 z-20"
          />
        </button>
      </div>
    </div>

    <dialog
      ref="dialog"
      class="p-8 mx-4 w-screen h-fit rounded-xl backdrop:bg-black/40"
    >
      <div class="w-full h-full flex flex-col">
        <button class="hover:ring self-end -mt-4" @click="dialog?.close()">
          <img src="/_tela01/Bt_X.svg" class="w-12 h-12 mb-2 z-20" />
        </button>
        <iframe
          class="w-full aspect-video mx-auto"
          src="https://www.youtube.com/embed/BIhdF4gR9bQ"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>
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

const mainBenefits = [
  { label: "Plano de Saúde", icon: "/_tela01/IconPlano.svg" },
  { label: "Previdência Privada", icon: "/_tela01/IconPrevidencia.svg" },
];

const dialog = ref<HTMLDialogElement>();
</script>
