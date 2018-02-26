<template>
	<select>
		<option></option>
		<option v-for="option in options" :value="option[optionsValueField]">{{ option[optionsTextField] }}</option>
	</select>
</template>
<script>

	import $ from 'jquery'
	import 'select2'

	export default {
		name: 'select2',
		props: {
			value: {},
			options: {},
			optionsValueField: { default: 'id'},
			optionsTextField: { default: 'text'},
			width: {default: '100%'},
			placeholder: {default: ''},
			allowClear: {}
		},
		mounted() {
			this.initialize();
		},
		watch: {
			value: function (value) {
				// update value
				$(this.$el).val(value).trigger('change');
			},
			options: function (options) {
				this.initialize();
			}
		},
		methods: {
			initialize() {
				var vm = this
				$(this.$el)
						.select2({
							width: this.width,
							placeholder: this.placeholder,
							allowClear: this.allowClear
						})
						.val(this.value)
						.trigger('change')
						.on('change', function () {
							vm.$emit('input', this.value)
						})
			}
		},
		destroyed: function () {
			$(this.$el).off().select2('destroy')
		}
	}
</script>
