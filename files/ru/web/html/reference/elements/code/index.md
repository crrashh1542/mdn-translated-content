---
title: "<code>: элемент отображения кода"
slug: Web/HTML/Reference/Elements/code
---

{{HTMLSidebar}}

**Элемент HTML `<code>`** отображает его содержимое в стиле, предназначенном для указания на то, что текст является коротким фрагментом компьютерного кода. По умолчанию текст содержимого отображается с использованием шрифта монопространства по умолчанию {{Glossary("user agent", "пользовательского агента")}}.

{{InteractiveExample("HTML Demo: &lt;code&gt;", "tabbed-shorter")}}

```html interactive-example
<p>
  The <code>push()</code> method adds one or more elements to the end of an
  array and returns the new length of the array.
</p>
```

```css interactive-example
code {
  background-color: #eee;
  border-radius: 3px;
  font-family: courier, monospace;
  padding: 0 3px;
}
```

| [Content categories](/ru/docs/Web/HTML/Guides/Content_categories) | [Flow content](/ru/docs/Web/HTML/Guides/Content_categories#flow_content), [phrasing content](/ru/docs/Web/HTML/Guides/Content_categories#phrasing_content), palpable content. |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Permitted content                                                 | [Phrasing content](/ru/docs/Web/HTML/Guides/Content_categories#phrasing_content).                                                                                             |
| Tag omission                                                      | Нет, открывающий и закрывающий теги обязательны.                                                                                                                              |
| Permitted parents                                                 | Any element that accepts [phrasing content](/ru/docs/Web/HTML/Guides/Content_categories#phrasing_content).                                                                    |
| Implicit ARIA role                                                | [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)                                                                                           |
| Permitted ARIA roles                                              | Any                                                                                                                                                                           |
| DOM interface                                                     | {{domxref("HTMLElement")}} Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the {{domxref("HTMLSpanElement")}} interface for this element.                         |

## Атрибуты

Этот элемент включает в себя только [глобальные атрибуты](/ru/docs/Web/HTML/Reference/Global_attributes).

## Пример

Текстовый абзац, включающий `<code>`:

```html
<p>
  The function <code>selectAll()</code> highlights all the text in the input
  field so the user can, for example, copy or delete the text.
</p>
```

Вывод, генерируемый этим HTML, выглядит так:

{{EmbedLiveSample("Example", 640, 70)}}

## Примечания

Для представления нескольких строк кода, оберните элемент `<code>` в элемент {{HTMLElement("pre")}}. Элемент `<code>` сам по себе представляет только один элемент кода или строку кода.

CSS-правило может быть определено для того, чтобы селектор `code` переопределил шрифт браузера по умолчанию. Предпочтения, установленные пользователем, могут иметь приоритет над указанными CSS.

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- {{HTMLElement("samp")}}
- {{HTMLElement("kbd")}}
- {{HTMLElement("command")}} (deprecated)
- {{HTMLElement("var")}}
- {{HTMLElement("pre")}}
