---
title: Привет!
comments: false
---

Насколько хорошо вы знаете TypeScript и его систему типов?
На этой странице собраны проблемы, для решения которых нужно использовать только типы в TypeScript.

Если вы хотите попробовать решить их самостоятельно, переходите в [репозиторий автора](https://github.com/type-challenges/type-challenges).
Там вы найдете проблемы, которые я ещё не успел решить и описать.

В случае, если вы застряли, можете посмотреть подробное решение с описанием здесь.
После решения, я также указываю ссылки на документацию TypeScript, где вы можете подробнее почитать о той или иной возможности языка, которая была использована для решения проблемы.

Если у вас есть вопросы, заметили ошибку или не поняли объяснение, пожалуйста, дайте об этом знать в [Issues](https://github.com/ghaiklor/type-challenges-solutions/issues).

{% assign challenges = site.pages | where: "lang", "ru" %}
{% include draw_challenges_table.html challenges = challenges %}
