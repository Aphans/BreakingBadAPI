<template>
  <br>
  <br>
    <form>
        <label class="relative block">
          <input
        :entrada="entrada"
        id="personaje"
        @input="updateProp('entrada', $event)"
        type="text"
        name="personaje"
        class="w-full bg-black placeholder:font-italitc border border-slate-400 drop-shadow-md rounded-md py-2 pl-3 pr-10 focus:outline-none"
                placeholder="Enter your character to search"/>
            <span class="absolute inset-y-0 right-0 flex items-center pr-3">
                <svg class="h-5 w-5 fill-white" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="30"
                    height="30" viewBox="0 0 30 30">
                    <path
                        d="M 13 3 C 7.4889971 3 3 7.4889971 3 13 C 3 18.511003 7.4889971 23 13 23 C 15.396508 23 17.597385 22.148986 19.322266 20.736328 L 25.292969 26.707031 A 1.0001 1.0001 0 1 0 26.707031 25.292969 L 20.736328 19.322266 C 22.148986 17.597385 23 15.396508 23 13 C 23 7.4889971 18.511003 3 13 3 z M 13 5 C 17.430123 5 21 8.5698774 21 13 C 21 17.430123 17.430123 21 13 21 C 8.5698774 21 5 17.430123 5 13 C 5 8.5698774 8.5698774 5 13 5 z">
                    </path>
                </svg>
            </span>
        </label>
    </form>
    <br>
    <span class="text-xs font-semibold inline-block py-1 px-2 uppercase rounded-full text-emerald-600 bg-emerald-200 last:mr-0 mr-1">
  Estamos buscando a {{entrada}}
</span>
    <br>
</template>
<script>
export default{
    name:'Buscador',
    emits: ["update:entrada"],
    props:{
            entrada: {
          type: String,
          required: true,
        },
        },
        methods:{
          updateProp(prop, { target: { value } }) {
          this.$emit(`update:${prop}`, value);
},
  }
    };
</script>
<style>
input{
    border:solid 1px;
    border-radius:2px;
}
</style>