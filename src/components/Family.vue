<template lang="html">
  <div class="col family">
    <div class="row photo">
      <img :src=family.photo>
    </div>
    <div class="row">
      <div class="col-6" v-for="person in family.names">
        <p class="h5 text-center font-weight-normal name">{{ person }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['family']
}
</script>

<style lang="css">
  div {
      border: 1px solid rgba(86, 61, 124, 0.2);
  }

  img {
    margin-left: auto;
    margin-right: auto;
    display: block;

    display: block;
    width: auto;
    height: auto;

    max-width:400px;
    max-height:300px;
  }

  @media (min-width: 800px) {
    img {
      max-width:800px;
      max-height:600px;
    }
  }

  .family {
    width: 400px;
  }

  @media (min-width: 800px) {
    .family {
      width: 800px;
      }  }

  .photo {
    width: 400px;
    height: 300px;
  }

  @media (min-width: 800px) {
    .photo {
      width: 800px;
      height: 600px;
      }  }

  .name {
    margin-top: 5px;
  }
</style>
