<template>
  <div class="has-background-black">
    <div class="container is-max-desktop">
      <a
        href="http://eskalation.gelungen.es"
        class="is-block p-5 has-text-white-bis"
      >
        <strong>Eskalation &middot; Rise Against the Machine</strong>:
        <span style="display: inline-block"
          >In Bewegung war die Treppe bisher nie!</span
        ></a
      >
    </div>
  </div>

  <footer class="footer">
    <div class="container is-max-desktop">
      <div class="columns">
        <div class="column">
          <div class="columns">
            <div class="column is-2 is-6-mobile">
              <img src="/images/stefan.jpg" alt="Bild Stefan Matheis" />
            </div>
            <div class="column">
              <p>Fragen? Anregungen? Presse. Sponsoring.</p>
              <p class="mt-4">
                <strong>Stefan Matheis</strong><br />
                <a :href="'mailto:' + mailAddress">✉️ {{ mailAddress }}</a
                ><br />
                <a href="tel:004916097048114">📞 +49 160 970 48 114</a>
              </p>

              <p
                v-if="$slots.default"
                class="mt-5 is-size-6 has-text-grey-light"
              >
                <slot />
              </p>
            </div>
          </div>
        </div>
      </div>

      <div id="events" class="grid is-row-gap-6 my-6">
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//www.fire-trail-nesselwang.de">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/fire-trail-nesselwang.svg"
                alt="Logo Fire Trail Nesselwang"
              />
            </figure>

            <span>Fire Trail</span>
            <span>Nesselwang</span>
          </a>
          <span class="tag mt-1 is-success">Sa, 10.10.26</span>
        </div>
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//www.fire-trail-nesselwang.de">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/schachmatt-ulm.svg"
                alt="Logo Schachmatt Ulm"
              />
            </figure>

            <span>Schachmatt</span>
            <span>Ulm</span>
          </a>
          <span class="tag mt-1">Februar '27</span>
        </div>
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//www.fire-trail-immenstadt.de">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/fire-trail-nesselwang.svg"
                alt="Logo Fire Trail Nesselwang"
              />
            </figure>

            <span>Fire Trail</span>
            <span>Immenstadt</span>
          </a>
          <span class="tag mt-1">Mai '27</span>
        </div>
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//muensterturmlauf-ulm.gelungen.es">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/muensterturmlauf-ulm.svg"
                alt="Logo Münsterturmlauf Ulm"
              />
            </figure>

            <span>Münsterturmlauf</span>
            <span>Ulm</span>
          </a>
          <span class="tag mt-1 is-info">Sa, 19.06.27</span>
        </div>
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//www.schachmatt-mannheim.de">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/schachmatt-ulm.svg"
                alt="Logo Schachmatt Ulm"
              />
            </figure>

            <span>Schachmatt</span>
            <span>Mannheim</span>
          </a>
          <span class="tag mt-1">Irgendwann '27</span>
        </div>
        <div class="cell has-text-centered" style="justify-self: center">
          <a href="//www.munich-sunrise.de">
            <figure class="image is-128x128">
              <img
                src="../assets/competitions/munich-sunrise.svg"
                alt="Logo Munich Sunrise"
              />
            </figure>

            <span>Munich</span>
            <span>Sunrise</span>
          </a>
          <span class="tag mt-1">Auch wieder '27</span>
        </div>
      </div>

      <div class="columns is-flex-direction-row-reverse">
        <div class="column">
          <p class="competitions has-text-grey-light has-text-right">
            … und alles begann 2023 mit dem
            <a
              href="//www.schanzenlauf-oberstdorf.de"
              style="color: inherit; display: inline-block"
            >
              <img
                src="../assets/competitions/schanzenlauf-oberstdorf.svg"
                alt="Logo Schanzenlauf Oberstdorf"
                style="height: 16px"
              />
              Schanzenlauf Oberstdorf</a
            >
          </p>
        </div>
        <div class="column">
          <p class="competitions has-text-grey-light has-text-right-mobile">
            Gelistet bei
            <a
              href="//firefighter-competitions.gelungen.es"
              style="color: inherit; display: inline-block"
            >
              <img
                src="../assets/firefighter-competitions.svg"
                style="height: 16px"
              />
              Firefighter Competitions</a
            >
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
const { mail, event } = defineProps(["event", "mail"]);

const mailAddress = computed(() =>
  (event?.organizer.email ?? mail).replace("mailto:", ""),
);
</script>

<style scoped>
#events a span {
  display: block;
}
.competitions span {
  display: block;
  padding-top: 3px;
}
.competitions img {
  filter: grayscale(1);
}
</style>
