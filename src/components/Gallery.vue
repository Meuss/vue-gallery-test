<template>
  <div>
    <img src="../assets/logo.svg" id="logo">
    <gallery :images="images" :index="index" @close="index = null" :options="options"></gallery>
    <div class="thumbnails">
      <div class="outer-image" v-for="(image, imageIndex) in images" :key="imageIndex">
        <div class="image" @click="index = imageIndex" :data-thumbnail="image | thumbnail">
          <svg version="1.1" class="magnifying" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 451 451" style="enable-background:new 0 0 451 451;" xml:space="preserve">
            <path d="M447.05,428l-109.6-109.6c29.4-33.8,47.2-77.9,47.2-126.1C384.65,86.2,298.35,0,192.35,0C86.25,0,0.05,86.3,0.05,192.3
              s86.3,192.3,192.3,192.3c48.2,0,92.3-17.8,126.1-47.2L428.05,447c2.6,2.6,6.1,4,9.5,4s6.9-1.3,9.5-4
              C452.25,441.8,452.25,433.2,447.05,428z M26.95,192.3c0-91.2,74.2-165.3,165.3-165.3c91.2,0,165.3,74.2,165.3,165.3
              s-74.1,165.4-165.3,165.4C101.15,357.7,26.95,283.5,26.95,192.3z"/>
          </svg>
        </div>
        <a :href="image | relativePath" :download="image | filename" class="dl-link" :title="image | filename">
          <svg version="1.1" class="download" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 59 59" style="enable-background:new 0 0 59 59;" xml:space="preserve">
            <g>
              <path d="M20.187,28.313c-0.391-0.391-1.023-0.391-1.414,0s-0.391,1.023,0,1.414l9.979,9.979C28.938,39.895,29.192,40,29.458,40
                c0.007,0,0.014-0.004,0.021-0.004c0.007,0,0.013,0.004,0.021,0.004c0.333,0,0.613-0.173,0.795-0.423l9.891-9.891
                c0.391-0.391,0.391-1.023,0-1.414s-1.023-0.391-1.414,0L30.5,36.544V1c0-0.553-0.447-1-1-1s-1,0.447-1,1v35.628L20.187,28.313z"/>
              <path d="M36.5,16c-0.553,0-1,0.447-1,1s0.447,1,1,1h13v39h-40V18h13c0.553,0,1-0.447,1-1s-0.447-1-1-1h-15v43h44V16H36.5z"/>
            </g>
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import VueGallery from "vue-gallery";

export default {
  data: function() {
    return {
      options: {
        closeOnSwipeUpOrDown: true
      },
      images: [
        "http://40gi.ch/gallery/gallery-img/IMG_0002.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0003.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0004.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0005.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0007.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0008.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0010.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0013.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0014.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0015.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0018.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0019.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0020.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0023.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0024.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0027.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0030.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0032.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0035.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0039.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0040.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0041.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0042.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0043.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0044.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0046.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0047.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0048.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0050.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0051.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0052.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0053.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0054.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0056.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0059.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0061.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0062.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0065.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_0066.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_7279.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9827.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9834.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9847.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9855.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9858.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9861.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9863.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9864.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9867.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9871.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9872.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9877.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9893.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9894.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9896.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9899.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9900.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9902.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9904.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9905.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9908.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9909.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9910.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9911.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9912.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9914.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9915.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9917.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9918.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9921.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9922.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9925.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9939.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9941.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9942.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9943.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9944.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9945.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9946.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9947.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9948.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9951.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9952.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9957.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9958.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9960.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9961.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9962.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9963.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9964.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9965.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9966.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9967.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9970.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9971.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9972.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9973.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9976.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9977.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9978.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9979.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9980.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9982.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9983.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9985.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9986.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9988.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9990.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9992.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9993.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9994.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9996.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_9997.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_10000.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_10001.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_10002.jpg",
        "http://40gi.ch/gallery/gallery-img/IMG_10003.jpg"
      ],
      index: null
    };
  },
  mounted() {
    Array.from(document.querySelectorAll(".image")).forEach(image => {
      image.style.backgroundImage = `url('${image.dataset.thumbnail}')`;
    });
  },
  filters: {
    filename: function(value) {
      const filename = value.replace("http://40gi.ch/gallery/gallery-img/", "");
      return filename;
    },
    relativePath: function(value) {
      const relativePath = value.replace("http://40gi.ch", "..");
      return relativePath;
    },
    thumbnail: function(value) {
      const thumb = value.replace(
        "http://40gi.ch/gallery/gallery-img/",
        "http://40gi.ch/gallery/gallery-img/thumb/"
      );
      return thumb;
    }
  },
  components: {
    gallery: VueGallery
  }
};
</script>

<style scoped lang="scss">
#logo {
  width: 200px;
  height: auto;
  margin-bottom: 30px;
}
.thumbnails {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  @media (max-width: 1036px) {
    justify-content: space-around;
  }
}
.outer-image {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 10px;
  .dl-link {
    display: inline-block;
    padding: 10px 20px 5px;
    svg {
      width: 20px;
      height: 20px;
      transition: transform 0.25s ease;
    }
    &:hover {
      svg {
        // transform: scale(1.1);
        path {
          fill: #4e8aaa;
        }
      }
    }
  }
}
// for fucking IE11 and iOS
.no-adownload .dl-link {
  display: none !important;
}
.image {
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
  width: 300px;
  height: 200px;
  cursor: pointer;
  transition: box-shadow 0.25s ease;
  box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16);
  position: relative;
  svg {
    opacity: 0;
    width: 20px;
    height: 20px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    transition: opacity 0.25s ease;
    path {
      fill: white;
    }
  }
  &:hover {
    box-shadow: 0 15px 60px 0 rgba(0, 0, 0, 0.2),
      0 15px 30px 0 rgba(0, 0, 0, 0.1);
    svg {
      opacity: 1;
    }
  }
}
@media (max-width: 768px) {
  .outer-image {
    margin: 10px 0;
    width: 100%;
  }
  .image {
    width: 100%;
    padding-top: 75%;
    height: auto;
    svg {
      opacity: 1;
      transform: none;
      left: auto;
      top: auto;
      bottom: 20px;
      right: 20px;
    }
  }
}
</style>
