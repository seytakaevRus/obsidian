### Базовый пример

Атрибут `ref` позволяет получить ссылку на DOM-элемент или на компонент. Это бывает полезно, если нужно программно сфокусировать ввод или сделать стороннюю библиотеку для элемента. `ref` будет лежать в `this.$refs`.

> Ссылку на элемент будет создана после монтирования компонента. Если попытаться получить доступ до этого времени, то вернется null. Это происходит, потому что элемент не существует до первого рендера. 

```js
mounted() {
	this.$refs.exampleInput.focus();
},
```

```html
<input type="text" ref="exampleInput" />
```

Благодаря коду выше при монтировании компонента фокус будет на элементе `<input />`.

### Ref в v-for

При использовании атрибута `ref` в `v-for` в `ref` будут храниться массив из ссылок на элементы.

Так, в следующем примере с задержкой в полсекунды переключается фокус у инпутов.

```js
data() {
	return {
		itemList: [
			{ name: 1, id: 'c9824f14-80ef-4020-8ea3-19aa7a62148a' },
			{ name: 2, id: '89db0fd8-9f04-4058-b055-d65f6a62a282' },
			{ name: 3, id: 'a119165b-dd48-4bf3-9325-d0c4d65569cf' },
		],
	};
},
mounted() {
	this.$refs.itemList.forEach((input, index) => {
		setTimeout(() => {
			input.focus();
		}, [500 * index]);
	});
},
```

```html
<template v-for="{name, id} in itemList" :key="id">
	<label :for="`${name}-${id}`">{{ name }}</label>
	<input :id="`${name}-${id}`" type="text" ref="itemList" />
</template>
```

### Ссылка в ref

В атрибут `ref` можно передать функцию, тогда при обновлении элемента будет вызвана эта функция.

Добавим к `data` метод, куда перенесем логику из `mounted`. Нужно каким-то образовать передавать индекс элемента, чтобы логика выше работала. Поэтому здесь используется атрибут `data`.

```js
methods: {
	setFocus(element) {
		const elementId = element.dataset.index;
		setTimeout(() => {
			element.focus();
		}, [500 * elementId])
	}
}
```

Также нужно заметить, что `ref` теперь используется с `v-bind`, потому что передается ссылка на функцию, а не строка.

<template v-for="{name, id} in itemList" :key="id">
	<label :for="`${name}-${id}`">{{name }}</label>
	<input :id="`${name}-${id}`" type="text" ref="itemList" />
</template>
```html
<template v-for="({name, id}, index) in itemList" :key="id">
	<label :for="`${name}-${id}`">{{ name }}</label>
	<input :id="`${name}-${id}`" type="text" :ref="setFocus" :data-index="index" />
</template>
```

---
Теги: #vue