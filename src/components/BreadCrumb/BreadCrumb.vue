<template>
	<div class="bread-crumb">
		<Breadcrumb separator=">">
			<BreadcrumbItem :to="item.to" :key="index" v-for="(item, index) in list"> {{ item.name }} </BreadcrumbItem>
		</Breadcrumb>
	</div>
</template>
<script>
import { Breadcrumb, BreadcrumbItem } from 'iview'

export default {
	name: 'bread-crumb',
	props: ['list'],
	// data 必须返回值，不然测试 coverage 会跳过该组件
	data() {
		return {}
	},
	components: {
		Breadcrumb,
		BreadcrumbItem
	}
}
</script>
<style lang="less" scoped>
.bread-crumb {
	height: 100%;
	min-height: 40px;
	max-height: 60px;
}
</style>
<style>
#wtia .ivu-breadcrumb-item-separator {
	color: #333;
}
</style>
