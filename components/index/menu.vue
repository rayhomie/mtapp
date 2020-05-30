<template>
  <div class="m-menu" @mouseleave="mouseleave">
    <dl class="nav">
      <dt>全部分类</dt>
      <dd v-for="(item,index) in menu" :key="index" v-if="index>0" @mouseenter="mouseenter">
        <i :class="item.type"></i>
        {{item.name}}
        <span class="arrow"></span>
      </dd>
    </dl>
    <div class="detail" v-show="kind">
      <template v-for="(item,index) in curdetail.child">
        <h4 :key="index">{{item.title}}</h4>
        <span v-for="v in item.child" :key="v">{{v}}</span>
      </template>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: "",
      menu: [
           {
          type: "",
          name: "",
          child: []
        },
        {
          type: "food",
          name: "美食",
          child: [
            {
              title: "美食",
              child: ["代金券", "饮食甜品", "火锅", "自助餐", "小吃快餐"]
            }
          ]
        },
        {
          type: "takeout",
          name: "外卖",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "hotel",
          name: "酒店",
          child: [
            {
              title: "酒店星级",
              child: ["经济型", "舒适/三星", "高档/四星", "豪华/五星"]
            }
          ]
        },
        {
          type: "homestay",
          name: "家居",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "movie",
          name: "电影",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "airport",
          name: "机票",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "ktv",
          name: "KTV",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "life",
          name: "生活服务",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "hair",
          name: "理发",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "marry",
          name: "婚庆",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "offspring",
          name: "温泉",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "sport",
          name: "健身",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "furniture",
          name: "家具",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "study",
          name: "学习服务",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "health",
          name: "健康",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        },
        {
          type: "bar",
          name: "酒吧",
          child: [{ title: "外卖", child: ["美团外卖"] }]
        }
      ]
    };
  },
  computed: {
    curdetail() {
      return this.menu.filter(item => item.type === this.kind)[0];
    }
  },
  methods: {
    mouseleave() {
      setTimeout(() => {
        this.kind = "";
      }, 150);
    },
    mouseenter(e) {
      this.kind = e.target.querySelector("i").className;
    }
  }
};
</script>

<style lang="scss">
</style>