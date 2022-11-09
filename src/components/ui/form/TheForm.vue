<template>
  <form class="form" novalidate="novalidate" @submit.prevent="submitForm">
    <div class="form__top">
      <the-input
        v-model.trim="fio.val"
        label="ФИО (отчество можно не указывать если нет)"
      />

      <fieldset class="d-flex align-items-center">
        <the-input
          v-model.trim="birthday.val"
          @keypress="getFormatInput('date', $event)"
          length="10"
          label="Дата рождения"
        />

        <the-radio-button-group :options="decisions" label="Пол" />
      </fieldset>
    </div>
    <div class="form__bottom">
      <h4>Паспортные данные</h4>

      <div class="form__wrapper d-flex align-items-center">
        <fieldset class="d-flex align-items-center">
          <the-input
            v-model.trim="passportRange.val"
            @keypress="getFormatInput('', $event)"
            length="4"
            label="Серия паспорта"
          />

          <the-input
            v-model.trim="passportNumber.val"
            @keypress="getFormatInput('', $event)"
            length="6"
            label="Номер"
          />
        </fieldset>

        <fieldset class="d-flex align-items-center">
          <the-input
            v-model.trim="unitNumber.val"
            @keypress="getFormatInput('dash', $event)"
            length="7"
            label="Номер подразделения"
          />

          <the-input
            v-model.trim="receiptDate.val"
            @keypress="getFormatInput('date', $event)"
            length="10"
            label="Дата выдачи"
          />
        </fieldset>
      </div>

      <the-input v-model.trim="address.val" label="Адрес регистрации" />

      <div class="form__btn-wrapper d-flex">
        <base-button title="Получить" type="submit" />
      </div>
    </div>
  </form>
</template>

<script>
import BaseButton from '../base/BaseButton.vue';
import TheInput from './TheInput.vue';
import TheRadioButtonGroup from './TheRadioButtonGroup.vue';

export default {
  components: {
    BaseButton,
    TheInput,
    TheRadioButtonGroup,
  },
  data() {
    return {
      fio: {
        val: 'Кириенко  Владимир Вячеславович',
      },
      birthday: {
        val: '12.12.2012',
      },
      passportRange: {
        val: '1236',
      },
      passportNumber: {
        val: '123666',
      },
      unitNumber: {
        val: '900-009',
      },
      receiptDate: {
        val: '12.12.2012',
      },
      address: {
        val: 'Респ Крым, пгт Массандра, г Ялта, ул Стахановская, д 15 к 2 кв 23',
      },
      decisions: ['Мужской', 'Женский'],
    };
  },

  methods: {
    submitForm() {},
    getFormatInput(input, event) {
      let inputLength = event.target.value.length;
      if (event.keyCode < 47 || event.keyCode > 57) {
        event.preventDefault();
      }
      if (inputLength !== 1 || inputLength !== 3) {
        if (event.keyCode == 47) {
          event.preventDefault();
        }
      }
      if (input === 'date') {
        if (inputLength === 2) {
          event.target.value += '.';
        } else if (inputLength === 5) {
          event.target.value += '.';
        }
      } else if (input === 'dash') {
        if (inputLength === 3) {
          event.target.value += '-';
        }
      }
    },
  },
};
</script>

<style scoped>
.form__bottom {
  margin-top: 40px;
}

fieldset + fieldset {
  margin-left: 40px;
}

.form__item + fieldset {
  margin-top: 16px;
}

fieldset .form__item + .form__item {
  margin-left: 16px;
}

fieldset .form__item {
  width: 100%;
}

fieldset .form__item:nth-child(odd) {
  max-width: 146px;
}

fieldset .form__item:nth-child(even) {
  max-width: 156px;
}

.form__wrapper {
  margin-bottom: 24px;
}

h4 {
  font-weight: 300;
  font-size: 20px;
  line-height: 40px;
  margin-bottom: 16px;
}

.form__btn-wrapper {
  margin-top: 56px;
}

@media (max-width: 767px) {
  .form__bottom {
    margin-top: 30px;
  }

  fieldset + fieldset {
    margin: 24px 0 0 0;
  }

  .form__item + fieldset {
    margin-top: 16px;
  }

  fieldset .form__item + .form__item {
    margin-left: 16px;
  }

  .form__wrapper {
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -webkit-box-align: start !important;
    -ms-flex-align: start !important;
    align-items: flex-start !important;
  }

  .form__btn-wrapper {
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
  }
}
@media (max-width: 575px) {
  .form__bottom {
    margin-top: 24px;
  }

  fieldset {
    width: 100%;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -webkit-box-align: start !important;
    -ms-flex-align: start !important;
    align-items: flex-start !important;
  }

  fieldset .form__item + .form__item {
    margin: 14px 0 0 0;
  }

  fieldset .form__item:nth-child(odd),
  fieldset .form__item:nth-child(even) {
    max-width: 100%;
  }
}
</style>
