<template>
  <footer class="footer p-0">
    <section class="section">
      <div class="container is-max-desktop">
        <div class="columns is-mobile">
          <div class="column is-4-mobile is-2-tablet">
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
          </div>
        </div>

        <p v-if="$slots.default" class="is-size-6 has-text-grey-light">
          <slot />
        </p>
      </div>
    </section>
  </footer>

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

  <footer class="footer p-0">
    <section class="section">
      <div class="container is-max-desktop">
        <div id="events" class="grid is-row-gap-6 mb-6">
          <div
            v-for="c in competitions"
            :key="c.name.join(' ')"
            class="cell has-text-centered"
            style="justify-self: center"
          >
            <component :is="c.url ? 'a' : 'div'" :href="c.url" class="name">
              <figure class="image is-128x128">
                <img :src="c.logo" :alt="c.alt ?? 'Logo ' + c.name.join(' ')" />
              </figure>

              <span v-for="part in c.name" :key="part">{{ part }}</span>
            </component>
            <span class="tag mt-1" :class="c.tag">{{ c.date }}</span>
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
    </section>
  </footer>
</template>

<script setup>
import eskalation from "../assets/competitions/eskalation.svg";
import fireTrail from "../assets/competitions/fire-trail-nesselwang.svg";
import muensterturmlauf from "../assets/competitions/muensterturmlauf-ulm.svg";
import munichSunrise from "../assets/competitions/munich-sunrise.svg";

// in chronological order; tag: is-success = bestätigt, is-info = vorläufig, ohne = alles andere
const competitions = [
  {
    name: ["Eskalation", "Frankfurt"],
    url: "//www.eskalation-frankfurt.de",
    logo: eskalation,
    date: "Februar '27",
  },
  {
    name: ["Fire Trail", "Immenstadt"],
    url: "//www.fire-trail-immenstadt.de",
    logo: fireTrail,
    date: "Mai '27",
  },
  {
    name: ["Münsterturmlauf", "Ulm"],
    url: "//muensterturmlauf-ulm.gelungen.es",
    logo: muensterturmlauf,
    date: "Sa, 19.06.27",
    tag: "is-info",
  },
  {
    name: ["Eskalation", "Essen"],
    url: "//www.eskalation-essen.de",
    logo: eskalation,
    date: "Sommer '27",
  },
  {
    name: ["Munich", "Sunrise"],
    url: "//www.munich-sunrise.de",
    logo: munichSunrise,
    date: "Auch wieder '27",
  },
  {
    name: ["One Left", "Mannheim"],
    logo: eskalation,
    date: "Irgendwann '27",
  },
  {
    name: ["Fire Trail", "Nesselwang"],
    url: "//www.fire-trail-nesselwang.de",
    logo: fireTrail,
    date: "Oktober '27",
  },
];

const { mail, event } = defineProps(["event", "mail"]);

const mailAddress = computed(() =>
  (event?.organizer.email ?? mail).replace("mailto:", ""),
);
</script>

<style scoped>
#events .name span {
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
