<template>
    <v-container>
        <p>{{titulo}}</p>
        <v-text-field v-model="nuevaTarea" ></v-text-field>
        <v-btn @click="agregarTarea"> Agregar</v-btn>

        <div  v-for='(item,id) in tareas' :key="id">
               
                        <Cards 
                  
             
                        />
                
        </div>
        
    </v-container>
</template>

<script>
  export default {
    data: () => ({
      titulo:'gym',
      tareas:[],
      nuevaTarea:'',
       datos:[
          {
              id:'0',
              nombre:'Test1',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'1',
              nombre:'Test2',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'2',
              nombre:'Test3',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'3',
              nombre:'Test4',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'4',
              nombre:'Test5',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'5',
              nombre:'Test6',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
          {
              id:'6',
              nombre:'Test7',
              direccion:'Direccion',
              status:'EN OBRA',
              desdeUSA:'$250,000 USA',
              hastaUSA:'$500,000 USA',
              desdeMXN:'$500,000 MXN',
              hastaMXN:'$1,000,000 MXN',        
              reveal: false, 
          },
        ],
    }),
    methods:{
        agregarTarea: function(){
            this.tareas.push({
                nombre:this.nuevaTarea,
                estado:false
            });
            this.nuevaTarea='';
        }
    }
  }
</script>

<style>

</style>