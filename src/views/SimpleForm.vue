<template>
  <div>
    <h1>Реквизиты счёта</h1>
    <form @submit.prevent="sendForm">
      <BaseInput v-model="requisites.name" label="Наименование организации" type="text" error="Обязательное поле"
        required />
      <BaseSelect :options="categories" v-model="requisites.category" label="ОГРН" error="Обязательное поле" required />
      <BaseInput v-model="requisites.ipn" label="ИНН" type="text" pattern="\d*" maxlength="10"
        error="Обязательное поле" required />
      <BaseInput v-model="requisites.kpp" label="КПП" type="text" pattern="\d*" error="Обязательное поле" maxlength="9"
        required />
      <BaseInput v-model="requisites.address" label="Юридический адрес" type="text" error="Обязательное поле"
        required />
      <BaseInput v-model="requisites.okpo" label="ОКПО" type="text" pattern="\d*" error="Обязательное поле"
        maxlength="8" required />
      <BaseInput v-model="requisites.account" label="Расчетный счет организации" type="text" pattern="\d*"
        error="Обязательное поле" maxlength="20" required />
      <BaseInput v-model="requisites.correspondent" label="Корреспондентский счет банка" type="text" pattern="\d*"
        error="Обязательное поле" maxlength="20" required />
      <BaseInput v-model="requisites.bik" label="БИК банка" type="text" pattern="\d*" error="Обязательное поле"
        maxlength="9" required />
      <button type="submit">Отправить</button>
    </form>
  </div>
</template>

<script>

export default {
  data() {
    return {
      categories: [
        'Растениеводство и животноводство, охота и предоставление соответствующих услуг в этих областях',
        'Лесоводство и лесозаготовки',
        'Рыболовство и рыбоводство'
      ],
      requisites: {
        category: '',
        name: '',
        ipn: '',
        kpp: '',
        address: '',
        okpo: '',
        account: '',
        correspondent: '',
        bik: ''

      }
    }
  },
  methods: {
    sendForm() {
      alert('Отправлено')
    }
  }
}
</script>
