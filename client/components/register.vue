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
		    <input type="text" class="form-control" id="login" placeholder="Введите Логин" name="login">
		  </div>
		  <div class="form-group">
		    <label for="password">Пароль</label>
		    <input type="password" class="form-control" id="password" placeholder="Введите пароль" name="password">
		  </div>
		  <div class="form-group">
		    <label for="password_repeat">Повтор пароля</label>
		    <input type="password" class="form-control" id="password_repeat" placeholder="Повторите пароль" name="repeat_password">
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
				event.preventDefault();
				let form = document.getElementById('reg_form');
				let login = form.login.value;
				let password = form.password.value;
				let repeat_password = form.password_repeat.value;
				if (password === repeat_password) {
					let promise = this.$auth.register(login, password);
					promise.then(function(){
						console.log("Registration success!");
						this.$router.push("/login");
					}).catch(function(response){
						console.log("Error");
						console.log(response);
					});
				}else{
					console.log("Пароли не совпадают")
				}
			}
		}
	}
</script>