<template>
	<main>
		<div class="container">
			<h1>欢迎使用Feng 待办事项</h1>
			<div class="input-add"></div>
			<input type="text" name="todo">
			<button>
				<i class="plus"></i>
			</button>
		</div>
		<div class="filters">
			<span class="filter active">全部</span>
			<span class="filter">已完成</span>
			<span class="filter">未完成</span>
		</div>
		<div class="todo-list">
			<div class="todo-item">
				<lable>
					<input type="checkbox">
					todo 1
					<span class="check-button"></span>
				</lable>
			</div>
			<div class="todo-item">
				<lable>
					<input type="checkbox">
					todo 2
					<span class="check-button"></span>
				</lable>
			</div>
			<div class="todo-item">
				<lable>
					<input type="checkbox">
					todo 3
					<span class="check-button"></span>
				</lable>
			</div>
		</div>
	</main>
</template>

<script>
	export default{
		name:"APP",
	};
</script>

<style>
	/* #app{
		font-family: Arial, Helvetica, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing:grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top:60px;
	} */
	*{
		box-sizing: border-box;
		margin: 0;
		padding: 0;
		font-family: helvetica,"PingFang SC","microsoft yahei",sans-serif;
	}
	/* 整个页面 */
	margin{
		width: 100vw;
		min-height: 100vm;
		display: grid;/* //布局 */
		align-items: center;
		justify-items: center;
		background: rgb(203,210,240);
	}
	.container{
		width: 60%;
		max-width: 400px;
		 box-shadow: 0px 0px 24px rgba(0,0,0,0.15);/*阴影 透明度 */
		 border-radius:24px;/*圆角 */
		padding: 48px 28px;
		background-color: rgb(245,246,252);
	}
	/* 标题 */
	h1{
		margin: 24px 0;
		font-size: 28px;/* 文字大小 */
		color: #414873;
		
	}
	/* 添加框 */
	 .input-add{/*添加框容器的样式 */
		position: relative;
		display: flex;
		align-items: center;
	}
	.input-add input{
		padding: 16px 52px 16px 18px;
		border-radius: 48px;
		border: none;
		outline: none;
		box-shadow: 0px 0px 24px rgba(0,0,0,0.08);
		width: 100%;
		font-size: 16px;
		color: #626262;
	}
	.input-add button{
		width: 46px;
		height: 46px;
		border-radius: 50%;
		background: linear-gradient(#c0a5f3,#7f95f7);
		border: none;
		outline: none;
		
		color: white;
		position: absolute;
		right: 0px;
		/* 小手 */
		cursor: pointer;
	}
	
	.input-add .plus{
		display: block;
		width: 100%;
		height: 100%;
		background: linear-gradient(#fff,#fff),linear-gradient(#fff,#fff);
		background-size: 50% 2px,2px 50%;
		background-position: center;
		background-repeat: no-repeat;
		
	}
	.filters{
		display: flex;
		margin: 24px 2px;
		color: #c0c2ce;
		font-size: 14px;
	}
    /* 每个过滤选项 */
	.filters .filter{
		margin-right: 14px;
		transition: 0.8s;
	}
	.filters .filter.active{
		color: #6b729c;
		transition: scale(1.2);
        /* //放大1.2倍 */
		
	}
	.todo-list{
        /* //grid布局 */
		display: grid;
		row-gap: 14px;
	}
	.todo-item{
		background: white;
		padding: 16px;
		border-radius: 8px;
		color: #626262;
	}
	.todo-item label{
		position: relative;
		display: flex;
		align-items: center;
	}
	.todo-item label span.check-button{
		position:  absolute;
		top: 0;
	}
	.todo-item label span.check-button::before,
	.todo-item label span.check-button::after{
		content: "";
		display: block;
		position: absolute;
		width: 18px;
		height: 18px;
		border-radius: 50%;
		
	}
	.todo-item label span.check-button::before{
		border: 1px solid #b382f9;
	}
	.todo-item label span.check-button::after{
		transition: 0.4s;
		background: #B382F9;
		transform: translate(1px,1px) scale(0.8);/* 缩小0.8 向下1px */
		opacity: 0;
	}
	 .todo-item input{/*原生复选框隐藏掉 */
		margin-right: 16px;
		opacity: 0;
	}
	 .todo-item input:checked+span.check-button::after{/*选中状态 */
		 opacity: 1;/*透明度为1 */
	}

</style>
