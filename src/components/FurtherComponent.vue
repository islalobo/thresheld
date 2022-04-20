<template>
  <div class="paragraph">
    As white settlers living on unceded indegenous land and disconnected from culturally rooted ancestral practices of our lineages, creative engagements with lineage-based work and practice are in service of attempting to account for legacies of harm and to heal from the toxic inheritances that keep us from cultivating the respectful and reciprocal relationships with the earth and people we dream of.
  </div>

  <div class="paragraph">
     This work experiments with creatively connecting with and integrating learnings from ancestral folklore and (queer)ecology in service navigating our own lives and relationships with more wholeness and dignity.
  </div>

  <div class="paragraph">
   Seal and selkie lore reflects an ancestral worldview that was animist and often involves themes of reinhabiting parts of ourselves we’ve been cut off from to preserve our safety or belonging, relationships between the human and non-human world, hybridity/shapeshifting, and lessons around harm and accountability. There is wisdom nestled there that feels pertinent to the challenges of being true to oneself and the work of dismantling the systems of domination that keep us from healing and liberation.
  </div>

  <div class="paragraph">
    Gratitude for the queer ancestors and trancestors that have towed the line, the plants and animals that are effortlessly queer by nature and the stories and folklore through which this is woven.
  </div>

  <div class="paragraph">
    <img
      :src="`https://${bucket}.s3.amazonaws.com/public/seals-transparent.png`"
      alt="Photo of parent and child viewed from behind standing on rocks at the ocean's edge. They are holding hands and looking off to the peach-coloured sunrise, with a circular apparition of seals in the distance."
      class="further-image"
    />
  </div>

  <div class="paragraph">
    Research and inspiration for this project drew on many sources, brilliant storyweavers and generative conversations.
    If interested in diving into some selkie lore and other good stuff that somehow shows up in this work, here are
    a few possibilities:

    <ul>
      <li>The People of the Sea, by David Thompson</li>
      <li>Bluiríní Béaloidis: National Folklore Collection Podcast, University College Dublin</li>
      <li>Undrowned: Black Feminist Lessons from Marine Mammals by Alexis Pauline Gumbs</li>
      <li>Biological Exuberance: Animal Homosexuality and Natural Diversity, Bruce Bagemihl</li>
      <li>“Homing: Returning to Oneself/Sealskin, Soulskin” in Women who Run with the Wolves, by Clarissa Pinkola Estés </li>
      <li>Queer Ecologies; Sex, Nature, Politics, Desire,  edited by Catriona Mortimer-Sandilands, Bruce Erickson</li>
    </ul>
  </div>

  <div class="paragraph">
    The films The Song of the Sea and The Secret of Roan Inish were fun to watch with kiddos & The Girl From the Sea is a sweet graphic novel by Molly Knox Ostertag featuring a selkie character and young queer love.
  </div>

  <div class="paragraph">
    Many thanks to the Center for Art Tapes’ Media Arts Scholarship and the wonderful crew of staff, educators, mentors and fellow artists at CFAT for helping to facilitate this project. Jesse Mitchell, Tori Flemming, Seamus Gallagher, Mable Wheeler, Joel Waddel, Kate Walchuk, Riss Sean Cruz, and Lou Sheppard–you are all stars. Thanks Alanna Macnevin for the website wizardry and support. Big smooches to N for diving in, hiking, recording, and making noises together.
  </div>
</template>

<script>
  document.getElementById('app').style.background  = '#F3C5C5';
  document.getElementById('app').style.backgroundSize  = "cover";  
  document.getElementById('app').style.color = "black";

  document.getElementById('nav-info').style.color = 'black';
  document.getElementById('nav-watch').style.color = 'black';
  document.getElementById('nav-explore').style.color = 'black';
  document.getElementById('nav-about').style.color = 'black';
  document.getElementById('nav-further').style.color = 'black';

  if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
    document.getElementById('app').style.height = "auto" ;
  } else {
    document.getElementById('app').style.height = "auto" ;
  }

  export default {
    name: 'FurtherComponent',
    data() {
      return {
        // bucket name
        bucket: process.env.VUE_APP_BUCKETEER_BUCKET_NAME,
      }
    },
    props: {
      msg: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .further-image {
    width: 100%;
  }
</style>