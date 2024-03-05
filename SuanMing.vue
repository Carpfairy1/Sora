<!-- App.vue -->
<template>
  <div class="container">
    <CardModel
      v-for="(item, index) in cards"
      :key="index"
      :image-src="item.image"
      :description="item.description"
      :intro="item.intro"

    />
  </div>
</template>

<script>
import CardModel from '@/components/CardModel.vue'
export default {
  components: {
    CardModel,
  },
  data() {
    return {
      cards: [
        // Add your card data here with image and description properties
        {
          image:require("../static/role1.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        {
          image: require("../static/role2.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image:require("../static/role3.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image: require("../static/role4.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image: require("../static/role5.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image: require("../static/role6.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image: require("../static/role7.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'

        },
        {
          image:require("../static/role8.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        {
          image: require("../static/role1.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        {
          image: require("../static/role2.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        {
          image: require("../static/role3.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        {
          image: require("../static/role4.png"),
          description: "William Afton",
          intro:'这是一段人物介绍'
        },
        // ...
      ],
    };
  },
};
</script>

<style scoped>
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  grid-gap: 16px;
  padding: 16px;
  margin-top:5vh ;
  margin-left: 9.5vw;

  max-width: 80vw;
}
.CardModel{
  margin-right: 3vw;
  /* margin-left: 5vw; */
}
</style>