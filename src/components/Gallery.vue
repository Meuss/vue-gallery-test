<template>
  <div>
    <img src="../assets/logo.svg" id="logo">
    <gallery :images="images" :index="index" @close="index = null" :options="options"></gallery>
    <div class="thumbnails">
      <div class="outer-image" v-for="(image, imageIndex) in images" :key="imageIndex">
        <div class="image" @click="index = imageIndex" :style="{ backgroundImage: 'url(' + image + ')' }">
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
        "http://40gi.ch/gallery/gallery-img/0002.jpg",
        "http://40gi.ch/gallery/gallery-img/0003.jpg",
        "http://40gi.ch/gallery/gallery-img/0004.jpg",
        "http://40gi.ch/gallery/gallery-img/0005.jpg",
        "http://40gi.ch/gallery/gallery-img/0007.jpg",
        "http://40gi.ch/gallery/gallery-img/0008.jpg",
        "http://40gi.ch/gallery/gallery-img/0010.jpg",
        "http://40gi.ch/gallery/gallery-img/0013.jpg",
        "http://40gi.ch/gallery/gallery-img/0014.jpg",
        "http://40gi.ch/gallery/gallery-img/0015.jpg",
        "http://40gi.ch/gallery/gallery-img/0018.jpg",
        "http://40gi.ch/gallery/gallery-img/0019.jpg",
        "http://40gi.ch/gallery/gallery-img/0020.jpg",
        "http://40gi.ch/gallery/gallery-img/0023.jpg",
        "http://40gi.ch/gallery/gallery-img/0024.jpg",
        "http://40gi.ch/gallery/gallery-img/0027.jpg",
        "http://40gi.ch/gallery/gallery-img/0030.jpg",
        "http://40gi.ch/gallery/gallery-img/0032.jpg",
        "http://40gi.ch/gallery/gallery-img/0035.jpg",
        "http://40gi.ch/gallery/gallery-img/0039.jpg",
        "http://40gi.ch/gallery/gallery-img/0040.jpg",
        "http://40gi.ch/gallery/gallery-img/0041.jpg",
        "http://40gi.ch/gallery/gallery-img/0042.jpg",
        "http://40gi.ch/gallery/gallery-img/0043.jpg",
        "http://40gi.ch/gallery/gallery-img/0044.jpg",
        "http://40gi.ch/gallery/gallery-img/0046.jpg",
        "http://40gi.ch/gallery/gallery-img/0047.jpg",
        "http://40gi.ch/gallery/gallery-img/0048.jpg",
        "http://40gi.ch/gallery/gallery-img/0050.jpg",
        "http://40gi.ch/gallery/gallery-img/0051.jpg",
        "http://40gi.ch/gallery/gallery-img/0052.jpg",
        "http://40gi.ch/gallery/gallery-img/0053.jpg",
        "http://40gi.ch/gallery/gallery-img/0054.jpg",
        "http://40gi.ch/gallery/gallery-img/0055.jpg",
        "http://40gi.ch/gallery/gallery-img/0056.jpg",
        "http://40gi.ch/gallery/gallery-img/0057.jpg",
        "http://40gi.ch/gallery/gallery-img/0058.jpg",
        "http://40gi.ch/gallery/gallery-img/0059.jpg",
        "http://40gi.ch/gallery/gallery-img/0060.jpg",
        "http://40gi.ch/gallery/gallery-img/0061.jpg",
        "http://40gi.ch/gallery/gallery-img/0062.jpg",
        "http://40gi.ch/gallery/gallery-img/0063.jpg",
        "http://40gi.ch/gallery/gallery-img/0064.jpg",
        "http://40gi.ch/gallery/gallery-img/0065.jpg",
        "http://40gi.ch/gallery/gallery-img/0066.jpg",
        "http://40gi.ch/gallery/gallery-img/9827.jpg",
        "http://40gi.ch/gallery/gallery-img/9828.jpg",
        "http://40gi.ch/gallery/gallery-img/9832.jpg",
        "http://40gi.ch/gallery/gallery-img/9833.jpg",
        "http://40gi.ch/gallery/gallery-img/9834.jpg",
        "http://40gi.ch/gallery/gallery-img/9835.jpg",
        "http://40gi.ch/gallery/gallery-img/9844.jpg",
        "http://40gi.ch/gallery/gallery-img/9847.jpg",
        "http://40gi.ch/gallery/gallery-img/9855.jpg",
        "http://40gi.ch/gallery/gallery-img/9858.jpg",
        "http://40gi.ch/gallery/gallery-img/9861.jpg",
        "http://40gi.ch/gallery/gallery-img/9863.jpg",
        "http://40gi.ch/gallery/gallery-img/9864.jpg",
        "http://40gi.ch/gallery/gallery-img/9867.jpg",
        "http://40gi.ch/gallery/gallery-img/9871.jpg",
        "http://40gi.ch/gallery/gallery-img/9872.jpg",
        "http://40gi.ch/gallery/gallery-img/9877.jpg",
        "http://40gi.ch/gallery/gallery-img/9893.jpg",
        "http://40gi.ch/gallery/gallery-img/9894.jpg",
        "http://40gi.ch/gallery/gallery-img/9896.jpg",
        "http://40gi.ch/gallery/gallery-img/9899.jpg",
        "http://40gi.ch/gallery/gallery-img/9900.jpg",
        "http://40gi.ch/gallery/gallery-img/9902.jpg",
        "http://40gi.ch/gallery/gallery-img/9904.jpg",
        "http://40gi.ch/gallery/gallery-img/9905.jpg",
        "http://40gi.ch/gallery/gallery-img/9908.jpg",
        "http://40gi.ch/gallery/gallery-img/9909.jpg",
        "http://40gi.ch/gallery/gallery-img/9910.jpg",
        "http://40gi.ch/gallery/gallery-img/9911.jpg",
        "http://40gi.ch/gallery/gallery-img/9912.jpg",
        "http://40gi.ch/gallery/gallery-img/9914.jpg",
        "http://40gi.ch/gallery/gallery-img/9915.jpg",
        "http://40gi.ch/gallery/gallery-img/9917.jpg",
        "http://40gi.ch/gallery/gallery-img/9918.jpg",
        "http://40gi.ch/gallery/gallery-img/9921.jpg",
        "http://40gi.ch/gallery/gallery-img/9922.jpg",
        "http://40gi.ch/gallery/gallery-img/9925.jpg",
        "http://40gi.ch/gallery/gallery-img/9926.jpg",
        "http://40gi.ch/gallery/gallery-img/9928.jpg",
        "http://40gi.ch/gallery/gallery-img/9931.jpg",
        "http://40gi.ch/gallery/gallery-img/9932.jpg",
        "http://40gi.ch/gallery/gallery-img/9939.jpg",
        "http://40gi.ch/gallery/gallery-img/9941.jpg",
        "http://40gi.ch/gallery/gallery-img/9942.jpg",
        "http://40gi.ch/gallery/gallery-img/9943.jpg",
        "http://40gi.ch/gallery/gallery-img/9944.jpg",
        "http://40gi.ch/gallery/gallery-img/9945.jpg",
        "http://40gi.ch/gallery/gallery-img/9946.jpg",
        "http://40gi.ch/gallery/gallery-img/9947.jpg",
        "http://40gi.ch/gallery/gallery-img/9948.jpg",
        "http://40gi.ch/gallery/gallery-img/9951.jpg",
        "http://40gi.ch/gallery/gallery-img/9952.jpg",
        "http://40gi.ch/gallery/gallery-img/9957.jpg",
        "http://40gi.ch/gallery/gallery-img/9958.jpg",
        "http://40gi.ch/gallery/gallery-img/9960.jpg",
        "http://40gi.ch/gallery/gallery-img/9961.jpg",
        "http://40gi.ch/gallery/gallery-img/9962.jpg",
        "http://40gi.ch/gallery/gallery-img/9963.jpg",
        "http://40gi.ch/gallery/gallery-img/9964.jpg",
        "http://40gi.ch/gallery/gallery-img/9965.jpg",
        "http://40gi.ch/gallery/gallery-img/9966.jpg",
        "http://40gi.ch/gallery/gallery-img/9967.jpg",
        "http://40gi.ch/gallery/gallery-img/9970.jpg",
        "http://40gi.ch/gallery/gallery-img/9971.jpg",
        "http://40gi.ch/gallery/gallery-img/9972.jpg",
        "http://40gi.ch/gallery/gallery-img/9973.jpg",
        "http://40gi.ch/gallery/gallery-img/9976.jpg",
        "http://40gi.ch/gallery/gallery-img/9977.jpg",
        "http://40gi.ch/gallery/gallery-img/9978.jpg",
        "http://40gi.ch/gallery/gallery-img/9979.jpg",
        "http://40gi.ch/gallery/gallery-img/9980.jpg",
        "http://40gi.ch/gallery/gallery-img/9982.jpg",
        "http://40gi.ch/gallery/gallery-img/9983.jpg",
        "http://40gi.ch/gallery/gallery-img/9985.jpg",
        "http://40gi.ch/gallery/gallery-img/9986.jpg",
        "http://40gi.ch/gallery/gallery-img/9988.jpg",
        "http://40gi.ch/gallery/gallery-img/9990.jpg",
        "http://40gi.ch/gallery/gallery-img/9992.jpg",
        "http://40gi.ch/gallery/gallery-img/9993.jpg",
        "http://40gi.ch/gallery/gallery-img/9994.jpg",
        "http://40gi.ch/gallery/gallery-img/9996.jpg",
        "http://40gi.ch/gallery/gallery-img/9997.jpg"
      ],
      index: null
    };
  },
  filters: {
    filename: function(value) {
      const filename = value.replace("http://40gi.ch/gallery/gallery-img/", "");
      return filename;
    },
    relativePath: function(value) {
      const relativePath = value.replace("http://40gi.ch", "..");
      return relativePath;
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
