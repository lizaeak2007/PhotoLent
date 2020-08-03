<style>
	#reg{
		background: red;
		width: 100%;
		border-color: grey;
	}
	input, #reg{
		box-shadow: 0 0 10px rgba(0,0,0,0.5);
	}
	form{
		width: 700px;
	}
	*{
		font-size: 25px;
	}
</style>

<template>
	<div>
		<form id="reg_form">
		  <div class="form-group" >
		    <label for="login">Логин</label>
		    <input type="text" class="form-control" id="login" placeholder="Введите Логин">
		  </div>
		  <div class="form-group">
		    <label for="password">Пароль</label>
		    <input type="password" class="form-control" id="password" placeholder="Введите пароль">
		  </div>
		  <div class="form-group">
		    <label for="password_repeat">Повтор пароля</label>
		    <input type="password" class="form-control" id="password_repeat" placeholder="Повторите пароль">
		  </div>
		  <button type="submit" class="btn btn-primary" id="reg" v-on:click="register">Зарегистрироваться!</button>
		</form>
	</div>
</template>

<script>
	module.exports={
		methods:{
			register: function() {
				console.log("register");
			}
		}
	}
</script>