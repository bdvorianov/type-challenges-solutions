---
id: 14
title: First of Array
lang: uk
level: easy
tags: array
---

## Завдання

Реалізувати тип `First<T>`, який приймає масив `T` і повертає тип його першого елемента.

Наприклад:

```ts
type arr1 = ['a', 'b', 'c']
type arr2 = [3, 2, 1]

type head1 = First<arr1> // 'a'
type head2 = First<arr2> // 3
```

## Розв'язок

Перше, що приходить в голову, це використати пошукові(або індексні) типи й просто написати `T[0]`:

```ts
type First<T extends any[]> = T[0]
```

Та це рішення не враховує один з випадків, який необхідно враховувати.
Якщо ми передамо порожній масив, `T[0]` не спрацює, бо не буде елементу з індексом 0(як і жодних інших).

Тож, перед тим, як використати тип першого елемента, нам потрібно перевірити, чи масив не порожній.
Для цього, ми можемо скористатись [умовними типами](https://www.typescriptlang.org/docs/handbook/advanced-types.html#conditional-types) в TypeScript.

Їх принцип доволі простий.
Якщо ми можемо присвоїти типу `T`(вхідний масив) порожній масив, це означає, що він порожній.
В такому випадку, ми повертаємо `never`, бо він нам не підходить. Немає елемента – немає типу.
І навпаки, якщо ми не можемо, значить масив містить елементи й ми спокійно можемо дізнатись тип першого з них.

```ts
type First<T extends any[]> = T extends [] ? never : T[0];
```

## Посилання

- [Типи пошуку/індексні типи](https://www.typescriptlang.org/docs/handbook/advanced-types.html#index-types)
- [Умовні типи](https://www.typescriptlang.org/docs/handbook/advanced-types.html#conditional-types)
