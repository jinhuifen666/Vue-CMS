<template>
	<div>
		<!--头部 -->
		<!-- 顶部固定导航栏 -->
    <mt-header fixed title="内容管理系统">
      <a slot="left">
        <mt-button icon="back">返回</mt-button>
      </a>
    </mt-header>

		<!-- 出口 -->
		<router-view class='content'></router-view>

	<!-- 底部导航菜单 -->
    <nav class="mui-bar mui-bar-tab">
			<router-link class="mui-tab-item" to="/home" @click.native="goPage('/home')">
				<span class="mui-icon mui-icon-home"></span>
				<span class="mui-tab-label">首页</span>
			</router-link>
			<router-link class="mui-tab-item" to="/vip" @click.native="goPage('/vip')">
				<span class="mui-icon mui-icon-contact"></span>
				<span class="mui-tab-label">会员</span>
			</router-link>
			<router-link class="mui-tab-item" to="/cart" @click.native="goPage('/cart')">
				<span class="mui-icon mui-icon-extra mui-icon-extra-cart">
          <span class="mui-badge">{{ $store.getters.allCount}}</span>
        </span>
				<span class="mui-tab-label">购物车</span>
			</router-link>
			<router-link class="mui-tab-item" to="/search" @click.native="goPage('/search')">
				<span class="mui-icon mui-icon-search"></span>
				<span class="mui-tab-label">搜索</span>
			</router-link>
		</nav>
	</div>
</template>

<script>
export default {
		 methods: {
    // 页面跳转
    goPage(path) {
      console.log('跳了');
      this.$router.push(path)
    }
  }
}
</script>

<style scoped>
/* 
添加 scoped后，style的样式只对当前组件起作用
只对页面中有的元素起作用的，动态生成的不起作用

*/
		.content{
			margin:40px 0 50px 0;
		}
</style>
