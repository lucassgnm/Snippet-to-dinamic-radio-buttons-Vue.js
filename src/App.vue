<template>
  <v-app>
    <h2 class="mb-2">Radio buttons dinâmicos</h2>
    <div class="ml-2">
      <div v-for="(comp, indexData) in arrData" v-bind:key="indexData">
        <div v-for="(item, indexComp) in comp.params" v-bind:key="indexComp">
          <input
            type="radio"
            v-model="comp.checked"
            :name="'comp-' + comp.idcomponent"
            :id="'item-' + item.item"
            :value="item.item"
          />
          <label class="ml-2" :for="'item-' + item.item"
            >Opção selecionada</label
          >
        </div>
        <div class="mt-1 mb-4">
          <b>-> Você selecionou o parameto: {{ comp.checked }}</b>
        </div>
      </div>
    </div>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      arrData: [
        {
          idcomponent: 25158,
          params: [{ item: 1 }, { item: 2 }, { item: 3 }, { item: 4 }],
          checked: 2,
        },
        {
          idcomponent: 895158,
          params: [{ item: 5 }, { item: 6 }, { item: 7 }, { item: 8 }],
          checked: 5,
        },
        {
          idcomponent: 14884,
          params: [{ item: 9 }, { item: 10 }, { item: 11 }, { item: 12 }],
          checked: 11,
        },
      ],
    };
  },
};
</script>