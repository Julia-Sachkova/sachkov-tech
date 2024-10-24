<template>
  <section class="section">
    <h2 class="section__title">Программа обучения</h2>

    <div>
      <UAccordion
        class="accordion"
        color="white"
        variant="soft"
        :size="$viewport.isLessThan('desktopMedium') ? 'lg' : 'xl'"
        multiple
        :items="firstItem"
        :ui="{
          default: {
            class: 'text-2xl w-full max-[540px]:text-lg',
          },
          item: {
            size: 'text-lg max-[540px]:text-base',
          },
          transition: {
            enterActiveClass: 'duration-500',
            leaveActiveClass: 'duration-500',
          },
        }"
      >
        <template #item="{ item }">
          <p v-thtml="item.content" class="text-white section__card"></p>
        </template>
      </UAccordion>

      <UAccordion
        class="accordion"
        color="white"
        variant="soft"
        :size="$viewport.isLessThan('desktopMedium') ? 'lg' : 'xl'"
        multiple
        :items="textItems"
        :ui="{
          default: {
            class:
              'text-2xl w-full max-[540px]:text-lg border-t rounded-none py-5 max-[1300px]:py-4',
          },
          item: {
            size: 'text-lg max-[540px]:text-base',
          },
          transition: {
            enterActiveClass: 'duration-500',
            leaveActiveClass: 'duration-500',
          },
        }"
      >
        <template #item="{ item }">
          <p v-thtml="item.content" class="text-white section__card"></p>
        </template>
      </UAccordion>

      <div class="section__total mt-6">
        Подробно изучи весь современный стэк на практике. Поработай с реальным
        проектом. Выполняй задачи и получай регулярное ревью.
      </div>
    </div>

    <LayoutStack />
  </section>
</template>

<script setup>
const { $viewport } = useNuxtApp();

const firstItem = [
  {
    label: "Архитектура бэкенд приложений",
    content: `<p>Мы подробно изучим и на практике разработаем большой проект,
						применяя современные архитектурные практики:
						<span class="programm-span">чистая архитектура</span>,
						<span class="programm-span">CQRS</span>,
						<span class="programm-span">DDD</span>,
						<span class="programm-span">модульный монолит</span> и
						<span class="programm-span">микросервисы</span>.  Постепенно мы
						перейдем от монолитной архитектуры к микросервисной.</p>`,
  },
];

const textItems = [
  {
    label: "Работа с базой данных",
    content: `<p>Практически ни одно бэкенд приложение не обходится без базы данных.
						В этом курсе мы подробно изучим как работать с
						<span class="programm-span">EF Core</span> и
						<span class="programm-span">Dapper</span>, проектировать базу
						данных, настривать сложные конфигурции, писать сложные запросы,
						управлять транзакциями и блокировками.</p>`,
  },
  {
    label: "ASP.NET Core",
    content: `<p>На этом курсе мы очень подробно изучим, как разрабатывать
						масштабируемые и производительные
						<span class="programm-span">Web API</span> приложения на
						<span class="programm-span">ASP.NET Core</span>. Вы научитесь
						работать с <span class="programm-span">конфигурацией</span>,
						<span class="programm-span">логированием</span>,
						<span class="programm-span">контроллерами</span>,
						<span class="programm-span">роутингом</span>,
						<span class="programm-span">middleware</span>,
						<span class="programm-span">аутентификацией</span> и
						<span class="programm-span">авторизацией</span>,
						<span class="programm-span">атрибутами</span> и
						<span class="programm-span">фильтрами</span>.</p>`,
  },
  {
    label: "Рельные бизнес задачи",
    content: `<p>Решение большого количества задач из реальной разработки. Вы на
						практике будете решать бизнес задачи:
						<span class="programm-span"> CRUD операции</span>,
						<span class="programm-span">
							взаимодействие между модулями</span
						>, <span class="programm-span"> валидация и ошибки</span>,
						<span class="programm-span"> состояния и события</span>.</p>`,
  },
  {
    label: "Инфраструктура",
    content: `<p>Сегодня современные веб приложения постоянно взаимодействуют с
						внешними сервисами, будь то
						<span class="programm-span">S3 хралище</span>, например
						<span class="programm-span">MinIO</span>, нереляционные базы
						данных, такие как <span class="programm-span">MongoDb</span> и
						<span class="programm-span">Redis</span>, брокеры сообщений -
						<span class="programm-span">Kafka</span> и
						<span class="programm-span">RabbitMQ</span>. Вы поймете, зачем и
						как правильно использовать внешние сервисы для вашего приложения.</p>`,
  },
  {
    label: "Тестирование",
    content: `<p>На курсе вы изучите, что такое
						<span class="programm-span">юнит</span> и
						<span class="programm-span">интеграционные тестирование</span>
						и на практике напишите тесты для своего веб приложения.</p>`,
  },
  {
    label: "Docker и Docker compose",
    content: `<p>Вы обязательно запустите своё приложение и множество различных
						сервисов в <span class="programm-span">Docker</span> с помощью
						<span class="programm-span">Docker compose</span>. Владение
						навыками и понимание контейнеризации сегодня является стандартом для
						каждого разработчика.</p>`,
  },
  {
    label: "Фоновые процессы и задачи",
    content: `<p>На курсе вы научитель работать с
						<span class="programm-span">background сервисами</span>,
						<span class="programm-span">Quartz</span> и
						<span class="programm-span">Hangfire</span> для работы с
						различными задачами и расписанием.</p>`,
  },
  {
    label: "Модульный монолит и микросервисы",
    content: `<p>Научись на практике создавать
						<span class="programm-span">модульные</span> и
						<span class="programm-span">распределённые системы</span> для
						достижения максимальной производительности и масштабируемости.
						Сегодня это ялвяется стандартом индустрии.</p>`,
  },
  {
    label: "Kafka, RabbitMq, Redis",
    content: `<p>На курсе вы освоите, как применять такие сложные технологии как:
						<span class="programm-span">Kafka</span>,
						<span class="programm-span">RabbitMq</span> и
						<span class="programm-span">Redis</span>. Благодаря
						<span class="programm-span">Redis</span> мы освоим
						распределённое кэширование. С помощью
						<span class="programm-span">RabbitMq</span> и
						<span class="programm-span">Kafka</span> мы сможем реализовать
						событийно ориентированную архитектуру.</p>`,
  },
  {
    label: "React, TypeScript и Tailwind",
    content: `<p>Сегодня очень ценятся именно
						<span class="programm-span">fullstack</span> разработчики.
						Поэтому на этом курсе мы изучим, как для вашего бэкенда сделать
						фронтенд на <span class="programm-span">React</span>. Вы
						разработаете полноценное фронтенд приложение и каждый сможет им
						воспользоваться.</p>`,
  },
  {
    label: "Redux, Axios, Rtk query",
    content: `<p>Здесь вы сможете на практике связать фронтенд приложение с бэкендом,
						отправлять запросы с помощью
						<span class="programm-span">axios</span> и
						<span class="programm-span">rtk query</span>, а также управлять
						состоянием приложения с помощью
						<span class="programm-span">Redux</span>.</p>`,
  },
  {
    label: "Резюме и собеседования",
    content: `<p>Всё шло к этому моменту, на курсе я подготовлю тебя к
						<span class="programm-span">собеседованиям</span> и помогу
						правильно составить <span class="programm-span">резюме</span>,
						чтобы ты точно получил свой догожданный
						<span class="programm-span">оффер</span>. Мы регулярно проводим
						мок собеседования и созвоны, где обсуждаем текущий рынок в it.</p>`,
  },
  {
    label: "CI/CD",
    content: `<p>Освой деплой своего приложения с помощью
						<span class="programm-span">Github Actions</span>. Ты на
						практике сможешь развернуть своё веб приложение, чтобы все могли им
						пользоваться!</p>`,
  },
];
</script>

<style scoped>
.section {
  display: flex;
  flex-direction: column;
  gap: 60px;
}

.section__title {
  font-size: 80px;
  font-weight: 800;
  line-height: 110%;
  background: linear-gradient(
    90deg,
    #e59cff 0.01%,
    #ba9cff 50.01%,
    #9cb2ff 100%
  );
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.section__card {
  border-radius: 12px;
  border: 1px solid #e59cff;
  background: rgba(10, 1, 25, 0.6);
  padding: 24px;
  font-size: 18px;
  font-weight: 400;
  color: #fff;
}

.section__total {
  border-radius: 12px;
  border: 1px solid #e59cff;
  background: linear-gradient(90deg, #c2b8ff 0%, #5a2bc7 100%);
  padding: 24px;
  color: #0a0119;
  text-align: center;
  font-size: 28px;
  font-weight: 600;
  line-height: 110%;
}

.section__card-title {
  background: linear-gradient(
    90deg,
    #e59cff 0.01%,
    #ba9cff 50.01%,
    #9cb2ff 100%
  );
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

@media screen and (max-width: 1300px) {
  .section {
    gap: 40px;
  }

  .section__title {
    font-size: 58px;
  }

  .section__card {
    padding: 20px;
  }

  .section__total {
    padding: 20px;
    font-size: 22px;
  }
}

@media screen and (max-width: 540px) {
  .section {
    gap: 24px;
  }

  .section__title {
    font-size: 28px;
  }

  .section__card {
    padding: 16px;
    font-size: 16px;
  }

  .section__total {
    padding: 16px;
    font-size: 18px;
  }
}
</style>
