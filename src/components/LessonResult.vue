<template>
  <section class="container__reg">
      <h2>{{$t('Results')}}</h2>
      <p><slot/></p>
      <p>{{$t('Note: you need to pass all lessons from course with one Polkadot.js account to apply for certificate')}}.</p>
  </section>
</template>

<style scoped>
  p {
      font-weight: bold;
  }
</style>