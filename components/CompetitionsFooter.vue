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

  <div class="trenner" aria-hidden="true"></div>

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

        <div class="hinweise">
          <div class="hinweis">
            <img :src="schachmatt" alt="" />
            <p>
              <a href="//www.schachmatt-ulm.de">Schachmatt Ulm</a>
              findet nicht mehr statt.
              <a href="//www.schachmatt-mannheim.de">Schachmatt Mannheim</a>
              wird es nicht geben – dafür kommt One Left Mannheim.
            </p>
          </div>
          <div class="hinweis">
            <img :src="firefighterCompetitions" alt="" />
            <p>
              <a href="//firefighter-competitions.gelungen.es"
                >Firefighter Competitions</a
              >
              – wo sich die Feuerwehr-Wettkampfszene trifft.
            </p>
          </div>
          <div class="hinweis">
            <img :src="schanzenlauf" alt="" />
            <p>
              Alles begann 2023 mit dem
              <a href="//www.schanzenlauf-oberstdorf.de"
                >Schanzenlauf Oberstdorf</a
              >.
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
import schachmatt from "../assets/competitions/schachmatt-ulm.svg";
import schanzenlauf from "../assets/competitions/schanzenlauf-oberstdorf.svg";
import firefighterCompetitions from "../assets/firefighter-competitions.svg";

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
.trenner {
  height: 2px;
  background: #dbdbdb;
}
#events .name span {
  display: block;
}
.hinweise {
  border-top: 1px solid #e5e5e5;
  padding-top: 1.5rem;
  display: grid;
  gap: 0.75rem;
}
.hinweis {
  display: flex;
  gap: 0.75rem;
  align-items: flex-start;
  font-size: 0.8rem;
  line-height: 1.5;
  color: #9a9a9a;
}
.hinweis img {
  flex: none;
  width: 20px;
  height: 20px;
  margin-top: 1px;
  filter: grayscale(1);
  opacity: 0.6;
}
.hinweis a {
  color: #6a6a6a;
  text-decoration: underline;
  text-decoration-color: #d0d0d0;
  text-underline-offset: 2px;
}
.hinweis a:hover {
  color: #363636;
}
</style>
