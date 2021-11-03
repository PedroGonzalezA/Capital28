<template>
    <v-dialog
          v-model="dialog"
          max-width="500px"
          :items="datos"
          
        >
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              color="#262d3c"
              dark
              class="mb-2"
              v-bind="attrs"
              v-on="on"
            >
              NUEVO DESSARROLLO
            </v-btn>
          </template>
          <v-card>
            <v-card-title>
              <span class="text-h5">{{ formTitle }}</span>
            </v-card-title>

            <v-card-text>
              <v-container>
                <v-row>
                  <v-col
                    cols="12"
                    sm="6"
                    md="4"
                  >
                    <v-text-field
                      v-model="nuevoComponente"
                      label="Nombre"
                    ></v-text-field>
                  </v-col>
                  
                </v-row>
              </v-container>
            </v-card-text>

            <v-card-actions>
              <v-spacer></v-spacer>
              <v-btn
                color="blue darken-1"
                text
                @click="close"
              >
                Cancelar
              </v-btn>
              <v-btn
                color="blue darken-1"
                text
                @click="agregarComponente"

              >
                Registrar
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>

</template>

<script>

  export default {
    
    data(){ 
      return{
        dialog: false,
        componente:[],
        nuevoComponente:'',
        editedIndex: -1,
  
      }
    },
    
    props:{
        nombre: {
          type: String,
          default:'Sin nombre',
          required:'true',
        },
    },

    computed: {
      formTitle () {
        return this.editedIndex === -1 ? 'Nuevo Desarrollo Inmobiliario' : 'Edit Item'
      },
    },

    watch: {
      dialog (val) {
        val || this.close()
      },
    },


    methods: {
     
      agregarComponente: function(){
            this.componente.push({
                nombre:this.nuevoComponente,
                estado:false
            });
            this.nuevoComponente='';
            this.$emit('update:nombre',this.nuevoComponente)
            
      },

      close () {
        this.dialog = false
        this.$nextTick(() => {
          this.editedItem = Object.assign({}, this.defaultItem)
          this.editedIndex = -1
        })
      },



       save () {
        if (this.editedIndex > -1) {
          Object.assign(this.datos[this.editedIndex], this.editedItem)
        } else {
          this.datos.push(this.editedItem)
        }
        this.close()
      },
    },
  }
</script>