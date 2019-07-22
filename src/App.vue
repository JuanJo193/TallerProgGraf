import VueFormGenerator from "vue-form-generator";

export default {
    components: {
        "vue-form-generator": VueFormGenerator.component
    }
};
<template>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        <h2 class="text-center">Formulario</h2>
        <table class="table text-center">
          <thead>
            <tr>
              <th>Nombre</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="gente in arrayGente" :key="gente.id">
              <td v-text="gente.nombre"></td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="col-md-6">
        <div class="form-group">
          <label for="nombre">Escribe tu nombre completo</label>
          <input type="text" id="nombre" placeholder="Escriba su nombre completo" required />
          <div class="form-group">
            <label for="ced">Cédula o pasaporte</label>
            <input type="text" id="ced" placeholder="Cédula o Pasaporte" required />
          </div>
          <div class="form-group">
            <label for="faculty">Escoja su Facultad</label>
            </div>
        </div>
        <button @click="Guardar()" class="btn btn-success">Añadir</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      arrayGente:[],
      schema:{
        fields: [{
            type: "input",
            inputType: "text",
            label: "Name",
            model: "name",
            placeholder: "Tu nombre",
            featured: true,
            required: true
        },
        {
            type: "input",
            inputType: "text",
            label: "Ced",
            model: "ced",
            placeholder: "Cédula o pasaporte",
            featured: true,
            required: true
        },
        {
           type: "select",
          label: "faculty",
           model: "faculty",
          values: ["Facultad de Ciencias de la Salud", "Facultad de Ingeniería, Arquitectura y Diseño", "Facultad de Ciencias Administrativas","Facultad de Gastronomío, Hotelerría y Turismo"]
          },
{
    type: "checkbox",
    label: "Status",
    model: "status",
    default: true
}]
    }
    }
  },
  methods:{
    Guardar(){
      var gente = {data} 
      this.arrayGente.push(gente);
      
      this.nombre = "";
    },
  }
}
</script>