<template>
  <div class="custom-tree-container">
    <div class="block">

      <!-- 1 el-tree -->
      <el-tree
        :data="data"
        show-checkbox
        node-key="id"
        default-expand-all
        :expand-on-click-node="false"
        :render-content="renderContent"
      >
      </el-tree>

    </div>
  </div>
</template>

<script>
let id = 1000;
export default {
  data() {
    const data = [
      {
        id: 1,
        label: "一级 1",
        children: [
          {
            id: 4,
            label: "二级 1-1",
            children: [
              {
                id: 9,
                label: "三级 1-1-1"
              },
              {
                id: 10,
                label: "三级 1-1-2"
              }
            ]
          }
        ]
      },
      {
        id: 2,
        label: "一级 2",
        children: [
          {
            id: 5,
            label: "二级 2-1"
          },
          {
            id: 6,
            label: "二级 2-2"
          }
        ]
      },
      {
        id: 3,
        label: "一级 3",
        children: [
          {
            id: 7,
            label: "二级 3-1"
          },
          {
            id: 8,
            label: "二级 3-2"
          }
        ]
      }
    ];
    return {
      data: JSON.parse(JSON.stringify(data)),
      data: JSON.parse(JSON.stringify(data))
    };
  },

  methods: {
    // onmouseenter:function(){
    // 		this.changeImg = !this.changeImg;
    // 		console.log('hello');
    //     },
    // onmouseenter:function(){
    //     this.changeImg = !this.changeImg;
    //     console.log('hello');
    // },

    // 2  追加元素
    renderContent(h, { node, data }) {
      return (
        <span class="custom-tree-node">
          <span>{data.label}</span>
          <span class="tubiao">
            <span>
              <img src="../public/img/icons/android-chrome-192x192.png" />
              12
            </span>
            <span>
              <img src="../public/img/icons/android-chrome-192x192.png" />
              34
            </span>
          </span>
        </span>
      );
    }
  }
};
</script>

<style scope="scoped">
/* 3 设置样式 */
.custom-tree-node {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 14px;
  padding-right: 8px;
}
.el-tree-node__content .tubiao {
  display: none;
}

.tubiao img {
  width: 20px;
  height: 20px;
  margin: 10px;
}
.el-tree-node__content:hover .tubiao {
  /* background-color: brown; */
  display: inline;
}
</style>