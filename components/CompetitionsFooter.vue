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

      <div class="is-hidden-desktop mt-6 mb-6">
        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//www.munich-sunrise.de">
                <img
                  src="../assets/competitions/munich-sunrise.svg"
                  alt="Logo Munich Sunrise"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a href="//www.munich-sunrise.de" style="display: block"
                >Munich Sunrise</a
              >
              <span class="tag mt-1 is-success">Sa, 25.07.26</span>
            </div>
          </div>
        </article>

        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//www.fire-trail-nesselwang.de">
                <img
                  src="../assets/competitions/fire-trail-nesselwang.svg"
                  alt="Logo Fire Trail Nesselwang"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a href="//www.fire-trail-nesselwang.de" style="display: block"
                >Fire Trail Nesselwang</a
              >
              <span class="tag mt-1 is-success">Sa, 10.10.26</span>
            </div>
          </div>
        </article>

        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//www.schachmatt-ulm.de">
                <img
                  src="../assets/competitions/schachmatt-ulm.svg"
                  alt="Logo Schachmatt Ulm"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a href="//www.schachmatt-ulm.de" style="display: block"
                >Schachmatt Ulm</a
              >
              <span class="tag mt-1">Februar '27</span>
            </div>
          </div>
        </article>

        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//www.fire-trail-immenstadt.de">
                <img
                  src="../assets/competitions/fire-trail-nesselwang.svg"
                  alt="Logo Fire Trail Nesselwang"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a href="//www.fire-trail-immenstadt.de" style="display: block"
                >Fire Trail Immenstadt</a
              >
              <span class="tag mt-1">Mai '27</span>
            </div>
          </div>
        </article>

        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//muensterturmlauf-ulm.gelungen.es">
                <img
                  src="../assets/competitions/muensterturmlauf-ulm.svg"
                  alt="Logo Münsterturmlauf Ulm"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a
                href="//muensterturmlauf-ulm.gelungen.es"
                style="display: block"
                >Münsterturmlauf Ulm</a
              >
              <span class="tag mt-1">Mai '27</span>
            </div>
          </div>
        </article>

        <article class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <a href="//www.schachmatt-mannheim.de">
                <img
                  src="../assets/competitions/schachmatt-ulm.svg"
                  alt="Logo Schachmatt Ulm"
              /></a>
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <a href="//www.schachmatt-mannheim.de" style="display: block"
                >Schachmatt Mannheim</a
              >
              <span class="tag mt-1">Irgendwann '27</span>
            </div>
          </div>
        </article>
      </div>

      <div class="is-hidden-touch columns competitions">

        <div class="column has-text-centered">
          <a href="//www.munich-sunrise.de">
            <img
              src="../assets/competitions/munich-sunrise.svg"
              alt="Logo Munich Sunrise"
            />
            <p>
              <span>Munich</span>
              <span>Sunrise</span>
            </p>
            <p>
              <span class="tag mt-2 is-success">Sa, 25.07.26</span>
            </p>
          </a>
        </div>

        <div class="column has-text-centered">
          <a href="//www.fire-trail-nesselwang.de">
            <img
              src="../assets/competitions/fire-trail-nesselwang.svg"
              alt="Logo Fire Trail Nesselwang"
            />
            <p>
              <span>Fire Trail</span>
              <span>Nesselwang</span>
            </p>
            <p>
              <span class="tag mt-2 is-success">Sa, 10.10.26</span>
            </p>
          </a>
        </div>

        <div class="column has-text-centered">
          <a href="//www.schachmatt-ulm.de">
            <img
              src="../assets/competitions/schachmatt-ulm.svg"
              alt="Logo Schachmatt Ulm"
            />
            <p>
              <span>Schachmatt</span>
              <span>Ulm</span>
            </p>
            <p>
              <span class="tag mt-2">Februar '27</span>
            </p>
          </a>
        </div>

        <div class="column has-text-centered">
          <a href="//muensterturmlauf-ulm.gelungen.es">
            <img
              src="../assets/competitions/muensterturmlauf-ulm.svg"
              alt="Logo Münsterturmlauf Ulm"
            />
            <p>
              <span>Münsterturmlauf</span>
              <span>Ulm</span>
            </p>
            <p>
              <span class="tag mt-2">Mai '27</span>
            </p>
          </a>
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
.competitions span {
  display: block;
  padding-top: 3px;
}
.competitions img {
  filter: grayscale(1);
}
</style>
