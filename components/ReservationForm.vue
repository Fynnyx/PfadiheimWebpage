<template>
  <div class="reservation-form">
      <form action="#">
          <label for="firstname">Vorname</label>
          <input type="text" id="firstname" placeholder="Vorname">

          <label for="lastname">Nachname</label>
          <input type="text" id="lastname" placeholder="Nachname">
          
      </form>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.reservation-form {
  form {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>