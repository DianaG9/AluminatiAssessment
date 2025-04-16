<script setup lang="ts">
import { ref } from 'vue'; //added ref  

const limit = ref(100); //made "limit" a ref 

function RandomNumbers() {
	let numbers = [];
	for (let i = 1; i <= limit.value; i++) {
		numbers.push(i);
	}
	return numbers.sort(() => Math.random() - 0.5);
}

function Hover(number: number) {
	const nums = document.querySelectorAll('.number');

	for(let i = 0; i < nums.length; i++)
	{
		const num = nums[i].textContent.trim();
		if(number % num === 0)
		{
		nums[i].classList.add('active')
		}
	}
}

function reset()
{
	const nums = document.querySelectorAll('.number');
	nums.forEach(num => num.classList.remove('active'))
}
</script>

<template>
		<h1>MathDivider</h1>
	<div>
		<input  class="input_num" type="number" v-model="limit" /><br /><br />
		<div class="number"
			:id="'number-'+number"
			v-for="number in RandomNumbers()"
			:key="number"
			@mouseover="Hover(number)"
			@mouseout="reset"
		>
			{{ number }}
		</div>
	</div>
</template>


