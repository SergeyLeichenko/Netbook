<template>
  <Form class="form" @submit="onSubmit" :validation-schema="schema">

    <div class="form__field">
      <label for="firstName" class="name">Ім'я</label>
      <Field name="firstName" type="text" id="firstName" placeholder="Введіть ім'я" class="input" />
      <ErrorMessage name="firstName" class="error" />
    </div>

    <div class="form__field">
      <label for="lastName" class="name">Прізвище</label>
      <Field name="lastName" type="text" id="lastName" placeholder="Введіть ім'я" class="input" />
      <ErrorMessage name="lastName" class="error" />
    </div>

    <div class="form__field">
      <label for="amount" class="name">Сума угоди</label>
      <Field name="amount" type="text" id="amount" placeholder="Введіть суму угоди" class="input" />
    </div>

    <div class="form__field">
      <label for="tin" class="name">ІПН</label>
      <Field name="tin" type="text" id="tin" placeholder="Введіть ІПН" class="input" />
      <ErrorMessage name="tin" class="error" />
    </div>

    <div class="agree">
      <Field name="agreement" type="checkbox" class="check-me" id="check-me" />
      <label for="check-me">Погоджуюсь з правилами та умовами</label>
    </div>

    <div class="form-btn">
      <button type="submit" class="btn">Відправити</button>
    </div>
  </Form>
</template>

<script setup>
import { Form, Field, ErrorMessage } from 'vee-validate';
import * as yup from 'yup';

const schema = yup.object({
  firstName: yup
    .string()
    .matches(/^[А-Яа-яЁёЇїІіЄєҐґ]+([-'][А-Яа-яЁёЇїІіЄєҐґ]+)*$/, 'Тільки кирилиця')
    .min(1, 'Мінімум 1 символ')
    .max(38, 'Максимум 38 символів')
    .required('Обов’язкове поле'),
  lastName: yup
    .string()
    .matches(/^[А-Яа-яЁёЇїІіЄєҐґ]+([-'][А-Яа-яЁёЇїІіЄєҐґ]+)*$/, 'Тільки кирилиця')
    .min(1, 'Мінімум 1 символ')
    .max(38, 'Максимум 38 символів')
    .required('Обов’язкове поле'),
  tin: yup
    .string()
    .matches(/^[0-9]+$/, 'Тільки цифри')
    .min(8, 'Мінімум 8 символів')
    .max(10, 'Максимум 10 символів')
    .required('Обов’язкове поле'),
  amount: yup
    .string()
    .matches(/^[0-9]*$/, 'Тільки цифри')
    .test('min-value', 'Мінімальне значення 1000', (value) => !value || Number(value) >= 1000)
    .test('max-value', 'Максимальне значення 1000000', (value) => !value || Number(value) <= 1000000)
    .notRequired(),
  agreement: yup
    .boolean()
    .oneOf([true], 'Підтвердіть згоду'),
});

const onSubmit = (values) => {
  console.log(JSON.stringify(values, null, 2));
}

</script>

<style lang="scss" scoped>
.form {
  max-width: 565px;
  margin: auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
  color: $light-gray;

  &__field {
    position: relative;

    .name {
      font-size: 12px;
      font-weight: 600;
    }

    .input {
      margin-top: 5px;
      width: 100%;
      border: 1px solid $input-border;
      padding: 15px;
      border-radius: 8px;

      &::placeholder {
        font-size: 16px;
      }
    }

    .error {
      color: red;
      font-size: 12px;
    }

    .icon-error {
      position: absolute;
      right: 10px;
      bottom: 28px;
    }
  }

  .agree {
    display: flex;
    align-items: center;
    margin: 30px 0;

    input {
      display: none;
    }

    label {
      position: relative;
      cursor: pointer;
      margin-left: 35px;

      &::before {
        display: block;
        content: "";
        width: 24px;
        height: 24px;
        border-radius: 8px;
        border: 1px solid $input-border;
        position: absolute;
        top: -4px;
        left: -35px;
      }
    }

    input:checked+label:after {
      display: block;
      content: url("../assets/images/check.svg");
      width: 20px;
      height: 20px;
      border-radius: 5px;
      position: absolute;
      top: -2px;
      left: -35px;
    }
  }

  .form-btn {
    margin: 0 auto;

    .btn {
      width: 170px;
    }
  }
}
</style>
