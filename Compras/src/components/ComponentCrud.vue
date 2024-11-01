<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Compras</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content style="background-color: #000000;" class="ion-padding">
      <ion-list>
     
        <ion-item>
          <ion-label position="stacked">Nombre del Producto</ion-label>
          <ion-input v-model="formData.ProductoName" placeholder="Nombre"></ion-input>
        </ion-item>

        <ion-item>
          <ion-label position="stacked">Cantidad</ion-label>
          <ion-input v-model="formData.Cantidad" placeholder="Cantidad"></ion-input>
        </ion-item>

        <ion-item>
          <ion-label position="stacked">Precio</ion-label>
          <ion-input type="number" v-model="formData.Precio" placeholder="Precio"></ion-input>
        </ion-item>

        <ion-item>
          <ion-label position="stacked">Descripcion</ion-label>
          <ion-textarea v-model="formData.reason" placeholder="Descripcion"></ion-textarea>
        </ion-item>

        <ion-item>
          <ion-label position="stacked">Categoria</ion-label>
          <ion-textarea v-model="formData.Categoria" placeholder="Categoria"></ion-textarea>
        </ion-item>

        <ion-item>
          <ion-label position="stacked">Cajero</ion-label>
          <ion-select v-model="formData.Cajero" placeholder="Cajero">
            <ion-select-option value="Juan">Maria</ion-select-option>
            <ion-select-option value="Camilo">Carlos</ion-select-option>
            <ion-select-option value="Carlos">leonardo</ion-select-option>
          </ion-select>
        </ion-item>

      

        <ion-item>
          <ion-label>Los productos son inportados</ion-label>
          <ion-checkbox slot="start" v-model="formData.termsAccepted"></ion-checkbox>
        </ion-item>
        <ion-item>
          <ion-label>Los productos son locales</ion-label>
          <ion-checkbox slot="start" v-model="formData.termsAccepted2"></ion-checkbox>
        </ion-item>
      </ion-list>

    
      <ion-button expand="block" @click="submitForm">Ingreso</ion-button>

      <ion-button expand="block" color="medium" @click="resetForm">Cancelar</ion-button>
    </ion-content>
  </ion-page>
</template>

<script>

export default {
  data() {
    return {
      formData: {
        ProductoName: '',
        Cantidad: '',
        Precio: '',
        reason: '',
        Categoria: '',
        Cajero: '',
        termsAccepted: false,
        termsAccepted2: false
      }
    };
  },
  methods: {
    submitForm() {
      if (
        this.formData.ProductoName &&
        this.formData.Cantidad &&
        this.formData.Precio &&
        this.formData.reason &&
        this.formData.Categoria &&
        this.formData.Cajero &&
        this.formData.termsAccepted &&
        this.termsAccepted2 
        
      ) {
        console.log('Datos del producto:', this.formData);
        this.resetForm(); 
      } else {
        console.log('Por favor, completa todos los campos obligatorios en el formato correcto y acepta los términos.');
      }
    },
    resetForm() {
      this.formData = {
        ProductoName: '',
        Cantidad: '',
        Precio: '',
        reason: '',
        Categoria: '',
        Cajero: '',
        termsAccepted: false,
        termsAccepted2: false
      };
    }
  }
}
</script>

<style scoped>
ion-button {
  margin-top: 10px;
}

</style>
