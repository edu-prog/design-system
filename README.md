<h1 align="center">
    Eduprog: Vue design system
</h1>

<div align="center">

[![CI](https://github.com/edu-prog/design-system/actions/workflows/ci.yml/badge.svg)](https://github.com/edu-prog/design-system/actions/workflows/ci.yml)

</div>

В дизайн системе предоставлены все необходимые компоненты и паттерны, которые используются в разработке front-end приложений Eduprog.

## 📋 Содержание

- [📦 Установка](#-установка)
- [🧱 Figma-компоненты](#-figma-компоненты)
- [🚗 Использование](#-использование)
- [📄 Документаиця](#-документация)
- [📲 Обновление](#-обновление)

## 📦 Установка

```bash
// with npm
npm install edu-prog/design-system --save

// with yarn
yarn add edu-prog/design-system --save
```

## 🧱 Figma-компоненты

Вы можете найти сверстанные figma компоненты по [ссылке](https://www.figma.com/file/B0RL6ptJLTX5CdzbxGou84/Design-system?node-id=2%3A120&viewport=525%2C722%2C0.37326961755752563).

## 🚗 Использование

Здесь Вы видите начальный пример:

```vue
<template>
  <div class="home">
    <Row>
      <Column>
        <Heading content="Регистрация" size="xl" />
      </Column>
    </Row>

    <Row>
      <Column>
        <TextInput type="text" label="Фамилия и Имя" mask="Иванов Иван" />
      </Column>
    </Row>

    <Row>
      <Column>
        <TextInput type="password" label="Пароль" />
      </Column>
    </Row>

    <Row>
      <Column>
        <Button content="Войти" type="main" size="l" />
      </Column>
    </Row>
  </div>
</template>

<script>
import Button from "eduprog-ds/src/components/Button.vue";
import Heading from "eduprog-ds/src/components/Heading.vue";
import TextInput from "eduprog-ds/src/components/TextInput.vue";

import { Row, Column } from "eduprog-ds/src/components/Grid.vue";

export default {
  name: "Home",
  components: {
    Button,
    Row,
    Column,
    TextInput,
    Heading,
  },
};
</script>
```

## 📄 Документация
Документация по дизайн-системе располагается на сайте: [ссылка](https://edu-prog.github.io/design-system/)

## 📲 Обновление

Если Вы хотите внести изменение в репозиторий, пожалуйста используйте для этого **GitHub Flow**:

- Создайте ветку
- Добавьте в ветку изменённые файлы
- зафиксируйте изменения
- отправьте в удаленный репозиторий

После этого откройте **pull request** и добавьте другого разработчика, в качестве Reviewer.
