<template>
	<div>
		<div class="xsyd-input-group">
			<label v-bind:for="inputId" class="xsyd-input-label">{{ label }}</label>
			<div v-if="isPwd === 'true'">
				<a-input-password
					class="xsyd-input-textview-password"
					v-bind:id="inputId"
					v-bind:placeholder="placeholderStr"
					v-bind:v-decorator="decorator"
					v-model="data"
				/>
			</div>
			<div v-else>
				<a-input
					type="text"
					class="xsyd-input-textview-normal"
					v-bind:id="inputId"
					v-bind:placeholder="placeholderStr"
					v-bind:v-decorator="decorator"
					v-model="data"
					><slot></slot
				></a-input>
			</div>
		</div>
	</div>
</template>
<script>
import "@/assets/css/widget/xsydInput.css";

export default {
	label: "label",
	inputId: "input1",
	isPwd: "false",
	decorator: "",
	placeholderStr: "fff",
	props: {
		label: String,
		inputId: String,
		isPwd: String,
		placeholderStr: String,
		decorator: String,
		default: "",
	},
	data() {
		return {
			data: "",
		};
	},
	methods: {},
};
</script>
