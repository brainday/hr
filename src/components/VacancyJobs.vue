<template>
<div class="cards">
  <div class="card">
    <div class="card__bottom">

      <p class="card__title">ГБУЗ ТО "ОКБ№1"</p>
      <p class="card__title">Врач-терапевт участковый</p>

      <div class="card__prices">
        <div class="card__price card__price--common">150 000</div>
      </div>
      <button class="card__add" @click="this.dialogState = true">Подробнее</button>
    </div>

    <GDialog max-width="400" scrollable="" v-model="dialogState">
                  <div class="dialog">
                    <span class="btn btn-default animate-load" data-event="jqm" data-name="resume" data-param-id="850" data-autoload-post="Врач-пульмонолог" data-autohide="">Отправить резюме</span>
                </div>
                </GDialog>
  </div>
</div>
</template>

<script>
import { GDialog } from 'gitart-vue-dialog'


export default {
  name: 'VacancyJobs',
  data() {
    return {
      dialogSuccess: true,
      dialogState: false,
    };
  },
  mounted() {
  },
  components: {
    GDialog
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.cards {
  display: grid;
  /* Автоматически заполняем на всю ширину grid-контейнера */
  grid-template-columns: repeat(auto-fill, 225px);
  width: 100%;
  max-width: 1000px; /* Ширина grid-контейнера */
  justify-content: center;
  justify-items: center; /* Размещаем карточку по центру */
  column-gap: 30px; /* Отступ между колонками */
  row-gap: 40px; /* Отступ между рядами */
  margin: 0 auto;
}
.card {
  width: 225px;
  height: 300px;
  display: flex;
  flex-direction: column;
  transition: 0.2s;
  position: relative;
  border-radius: 12px;
  box-shadow: 0 0.5rem 1rem rgba(0,0,0,.15);
}

/* При наведении на карточку - меняем цвет тени */
.card:hover {
  box-shadow: 4px 8px 16px rgba(201, 147, 42, 0.2);
}

.card__bottom {
  display: flex;
  flex-direction: column;
  flex: 1 0 auto; /* Занимаем всю оставшуюся высоту карточки */
  padding: 10px;
}

.card__prices {
  display: flex;
  margin-top: 40px;
  justify-content: center;
}

.card__price::after {
  content: "₽";
  margin-left: 4px;
  position: relative;
}

.card__price--common {
  font-weight: 400;
  font-size: 17px;
  color: #606060;
  display: flex;
  flex-wrap: wrap-reverse;
  justify-content: flex-end;
}

.card__price--common::before {
  content: "Зарплата от ";
  font-weight: 400;
  font-size: 17px;
  color: #787878;
  padding-right: 10px;
}

.card__title {
  display: block;
  margin-bottom: 10px;
  font-weight: 400;
  font-size: 17px;
  line-height: 150%;
  color: #414141;
}

.card__title:hover {
  color: rgb(201, 147, 42);
}

.card__add {
  display: block;
  width: 100%;
  font-weight: 400;
  font-size: 17px;
  color: #304171;
  padding: 10px;
  text-align: center;
  border: 1px solid #304171;
  border-radius: 4px;
  cursor: pointer; /* Меняем курсор при наведении */
  transition: 0.2s;
  margin-top: auto; /* Прижимаем кнопку к низу карточки */
}

.card__add:hover {
  border: 1px solid #c9932a;
  background-color: #c9932a;
  color: #fff;
}
</style>
