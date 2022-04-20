<template>
  <div class="paragraph">
    <img
      :src="`https://${bucket}.s3.amazonaws.com/public/still.jpeg`"
      alt="Photo of parent and child viewed from behind standing on rocks at the ocean's edge. They are holding hands and looking off to the peach-coloured sunrise, with a circular apparition of seals in the distance."
      class="about-image"
    />
  </div>

  <div class="paragraph">
    This work was created in relationship with the water, the land and creatures of Mi’kma’ki, the traditional,
    unceded and unsurrendered territory of the Mi’kmaq. We live here in gratitude and endeavor, as treaty people,
    to continue the work of cultivating respectful relationships with all people as outlined in the Peace and
    Friendship Treaties.
  </div>

  <div class="paragraph">
    <strong>Kit Holden-Ada</strong> is a multidisciplinary settler artist and craftsperson of Scottish/Irish/English
    ancestry born and raised on the prairies (Treaty 2) and currently based in Kjiputktuk, Mi’kma’ki
    (Halifax, NS). As a working parent and artist they maintain slow engagement with sound, movement,
    and installation-based work that centers curious explorations of (queer) relationality, lineage,
    practice and play. A trained metalsmith, Kit has been producing a line of jewellery
    (<a href="http://www.fervoursown.com/" target="_blank">Fervour’s Own Jewellery</a>) since 2011. With appreciation
    for working in close relationship with the body and the elements, Kit approaches
    craftwork and hand making as embodiment practices. 
  </div>

  <div class="paragraph">
    <strong>N Ada</strong> is a curious and creative almost-13-year-old and a seasoned collaborator (big sibling).
    She is currently into reading, playing violin, baking and exploring her expanding world. 
    Her melodies brought all the seals to the yard.
  </div>
</template>

<script>
  const bucket = process.env.VUE_APP_BUCKETEER_BUCKET_NAME;
  
  document.getElementById('app').style.background  = `url('https://${bucket}.s3.amazonaws.com/public/pinkwater.gif')`;
  document.getElementById('app').style.backgroundSize  = "cover";
  document.getElementById('app').style.height = "auto";
  document.getElementById('app').style.color = "ghostwhite";

  if ( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator?.userAgent) ) {
    document.getElementById('app').style.height = "auto" ;
  } else {
    document.getElementById('app').style.height = "auto" ;
  }

  export default {
    name: 'AboutComponent',
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
  .about-image {
    width: 100%;
  }
</style>