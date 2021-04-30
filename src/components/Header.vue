<template>
  <header>
    <div>
      <!-- As a heading -->
      <b-navbar variant="success" type="light">
        <b-navbar-brand tag="h1" class="mb-0 mx-auto">
          <h1 class="display-4">
            <i class="fa fa-viruses"></i> Covid-19 Tracker
          </h1>
          <p class="text-center">
            API by
            <a
              class="text-dark"
              href="https://covid19api.com"
              target="_blank"
              > covid19api.com</a
            >
          </p>
        </b-navbar-brand>
      </b-navbar>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>