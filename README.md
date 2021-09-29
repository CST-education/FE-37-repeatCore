# FE-37-repeatCore

// Примитивы копируются
const a = 5
const b = a

// Объекты передают ссылку на себя, не копируюся просто так
const objA = {
  key: 'A',
}
const objB = objA

// все объект - и массив, и сам объект и даже функция

// Ключевые методы работы с массивами
// .slice() || ... (SPREAD) - полноценная копия массива
// функциональные методы
// .map() => копия массива той же длины - срез значений
// .forEach() => ничего не возвращает, просто перебирает массив
// .filter() => всегда копию массива, но только тех элементов, что прошли условие, или []
// .find() => первый элемент массива, прошедший условие или undefined
// .reduce() => вернет тот тип данных через обязательный параметр acc,
// что указан вторым аргументом, после колбека - "", 0, {}, []

// .some() => true || false - по принципу логического ||
// .every() => true || false - по принципу логического &&
// .sort() => МУТИРУЕТ исходный массив

// методы Object
// Object.create() - новый объект с прототипом исходного
// Object.keys() => [key1, ..., keyN]
// Object.values() => [value1, ..., valueN]
// Object.entries() => [[key1, value1], ..., [keyN, valueN]]

// ПРОВЕРКА УСЛОВИЙ
// if(condition) return value - Guard Clause
// if(condition){true} else{false} || consdition ? (true) : (false)
// switch(value){
//     case "":
//         statement;
//         break
//         default:
//             statement
// }

// ФУНКЦИИ
// function Declaration - hoisting
// function Expression  - const || let
// Arrow funсtion - short function Expression ()=>{}

// this
// function Declaration & function Expression - this при вызове
// Arrow funсtion - при создании (объявлении)

// ОСНОВНЫЕ ПАРАДИГМЫ (ПОДХОДЫ)
// ООП (классы) и Декларативная (функции)

// ООП (классы)
// прототипное наследование свойств и методов от предков

// Декларативная (функции) - замыкание (CLOSURE) - способность функции видеть и изменять значение
// переменной из той же области видимости, где они обе объявлены

const user = {
  _name: 'user',
  get name() {
    return this._name
  },
  set name(value) {
    return (this._name = value)
  },
}
// user._name - ПЛОХАЯ ПРАКТИКА
// user.name - использование геттера - ХОРОШО
// user.name = "new user" - использование сеттера - ХОРОШО

function updateUser() {
  const name = 'user'
  function getName() {
    return name
  }
  function setName(value) {
    return (name = value)
  }
}

// DOM

// get 1 element (Node)
// document.querySelector('tag' || '.class' || '#id' || '[attr="value"]')
// document.getElementById('id')

// get collection (pseudo[])
// document.querySelectorAll('tag' || '.class' || '#id' || '[attr="value"]')
// document.getElementsByClassName('class')

// create Element
// document.createElement('name')

// create Markup
// const template = `<div>${value}</div>`

// update
// class by .classList.add('class')
// class by .classList.remove('class')
// class by .classList.toggle('class')
// class by .classList.replace('oldClass', 'newClass')

// attr by setAttribute("attr", "value")
// inline styles by .style.color, etc.... - Be Carefull!!!

// text || innerNode by .textContent = 'value'

// delete Element
// old: parentNode.removeChild(child)
// new: element.remove()

// delete Markup
// .innerHTML = ""

// Встраивание разметки

// для элментов (ОБЪЕКТОВ)

// .before() - перед элементом
// .insertAdjacentElement("beforebegin", child)

// .prepend(...children) - в начало
// .insertAdjacentElement("afterbegin", child)

// .appendChild(child) - в конец
// .append(...children) - в конец
// .insertAdjacentElement("beforeend", child)

// .after() - за элементом
// .insertAdjacentElement("afterend", child)

// для строчной разметки
// .innerHTML - - Be Carefull!!! полный перерендер
// .insertAdjacentHTML("beforebegin", child)
// .insertAdjacentHTML("afterbegin", child)
// .insertAdjacentHTML("beforeend", child)
// .insertAdjacentHTML("afterend", child)
