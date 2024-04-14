<script setup lang="ts">
enum Gender {
  JUNGE = "Junge",
  MÄDCHEN = "Mädchen",
}

enum Populatity {
  TRENDY = "Trendy",
  EINZIGARTIG = "Einzigartig",
}

enum Length {
  SHORT = "Kurz",
  LONG = "Lang",
  BOTH = "Egal",
}

interface OptionsState {
  gender: Gender;
  popularity: Populatity;
  length: Length;
}

const options = reactive<OptionsState>({
  gender: Gender.JUNGE,
  popularity: Populatity.EINZIGARTIG,
  length: Length.LONG,
});
</script>

<template>
  <div class="container">
    <h1>Baby Namen Generator</h1>
    <p>
      Wähle eine der folgenden Optionen und klick auf den "Finde Namen" Button
      unten.
    </p>
    <div class="options-container">
      <div class="option-container">
        <h3>1) Wähle ein Geschlecht</h3>
        <div class="option-buttons">
          <button
            class="btn btn-left"
            :class="options.gender === Gender.JUNGE && 'btn-active'"
          >
            Junge
          </button>
          <button
            class="btn btn-right"
            :class="options.gender === Gender.MÄDCHEN && 'btn-active'"
          >
            Mädchen
          </button>
        </div>
      </div>
      <div class="option-container">
        <h3>2) Wähle die Beliebtheit des Namens</h3>
        <div class="option-buttons">
          <button
            class="btn btn-left"
            :class="options.popularity === Populatity.TRENDY && 'btn-active'"
          >
            Trendy
          </button>
          <button
            class="btn btn-right"
            :class="
              options.popularity === Populatity.EINZIGARTIG && 'btn-active'
            "
          >
            Einzigartig
          </button>
        </div>
      </div>
      <div class="option-container">
        <h3>3) Wähle die Länge des Namens</h3>
        <div class="option-buttons">
          <button
            class="btn btn-left"
            :class="options.length === Length.LONG && 'btn-active'"
          >
            Lang
          </button>
          <button
            class="btn"
            :class="options.length === Length.BOTH && 'btn-active'"
          >
            Alles
          </button>
          <button
            class="btn btn-right"
            :class="options.length === Length.SHORT && 'btn-active'"
          >
            Kurz
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  font-family: Arial, Helvetica, sans-serif;
  color: rgb(255, 255, 255);
  max-width: 50rem;
  margin: 0 auto;
  text-align: center;
}

.container h1 {
  font-size: 3rem;
}

.options-container {
  background-color: rgb(67, 65, 65);
  border-radius: 2rem;
  padding: 2rem;
  width: 95%;
  margin: 0 auto;
  margin-top: 4rem;
  position: relative;
}

.option-container {
  margin-bottom: 2rem;
}

.btn {
  background-color: aliceblue;
  outline: 0.15rem solid rgb(249, 87, 89);
  border: none;
  padding: 0.75rem;
  width: 12rem;
  font-size: 1rem;
  color: rgb(67, 65, 65);
  cursor: pointer;
  font-weight: 200;
}

.btn-left {
  border-radius: 1rem 0 0 1rem;
}

.btn-right {
  border-radius: 0 1rem 1rem 0;
}

.btn-active {
  background-color: rgb(249, 87, 89);
  color: whitesmoke;
}
</style>
