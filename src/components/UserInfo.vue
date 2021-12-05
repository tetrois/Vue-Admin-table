<template>
  <div>
    <tr>
      <td class="description">Короткий джобкод :</td>
      <td class="data">{{ getPropertyData("short_jobcode") }}</td>
      <td class="description">ФИО:</td>
      <td class="data">{{ getPropertyData("fio") }}</td>
      <td class="description">Тип сотрудника:</td>
      <td class="data">{{ getPropertyData("sf_type_of_employee") }}</td>
    </tr>
    <tr>
      <td class="description">Код ВСП:</td>
      <td class="data">{{ getPropertyData("vspcode") }}</td>
      <td class="description">Джобкод:</td>
      <td class="data">{{ getPropertyData("jobcode") }}</td>
      <td class="description">Дата создания:</td>
      <td class="data">{{ getPropertyData("created_at") }}</td>
    </tr>
    <tr>
      <td class="description">TБ:</td>
      <td class="data">{{ getPropertyData("tb_name") }}</td>
      <td class="description">Табельный номер:</td>
      <td class="data">{{ getPropertyData("sapid") }}</td>
      <td class="description">Дата обновления:</td>
      <td class="data">{{ getPropertyData("updated_at") }}</td>
    </tr>
    <tr>
      <td class="description">Код TБ:</td>
      <td class="data">{{ getPropertyData("tb") }}</td>
      <td class="description">Логин:</td>
      <td class="data">{{ getPropertyData("login") }}</td>
      <td class="description">Дата иницилизации:</td>
      <td class="data">{{ getPropertyData("init_time") }}</td>
    </tr>
    <tr>
      <td class="description">ГОСБ:</td>
      <td class="data">{{ getPropertyData("gosb") }}</td>
      <td class="description">Email:</td>
      <td class="data">{{ getPropertyData("email") }}</td>
      <td class="description">Дата найма:</td>
      <td class="data">{{ getPropertyData("") }}</td>
    </tr>
    <tr>
      <td class="description">Организация:</td>
      <td class="data">{{ getPropertyData("organization") }}</td>
      <td class="description">Дата рождения:</td>
      <td class="data">{{ getPropertyData("birthDate") }}</td>
      <td class="description">Дата увольнения:</td>
      <td class="data">{{ getPropertyData("hire_date") }}</td>
    </tr>
    <tr>
      <td class="description">Должность:</td>
      <td class="data">{{ getPropertyData("synonym") }}</td>
      <td class="description"></td>
      <td class="data" >{{ }}</td>
      <td class="description">Доступы</td>
      <td>
          <span class="label" :class="{'label-success': Boolean(getPropertyData(`rb`)), 'label-danger': !Boolean(getPropertyData(`rb`))}">РБ</span>
          <span class="label" :class="{'label-success': Boolean(getPropertyData(`sbs`)), 'label-danger': !Boolean(getPropertyData(`sbs`))}">ВШС</span>
          <span class="label" :class="{'label-success': Boolean(getPropertyData(`atd`)), 'label-danger': !Boolean(getPropertyData(`atd`))}">АТД</span>
      </td>
    </tr>
  </div>
</template>


<script>
export default {
  data() {
    return {
      userDataFull: {
        data: [
          
        ],
        links: {
        },
        meta: {
        },
        included: [
          
          {
            id: 49563,
            type: "user",
            attributes: {
              user_exists: true,
              fio: "\u041e\u0440\u043b\u043e\u0432\u0441\u043a\u0430\u044f \u0421\u0432\u0435\u0442\u043b\u0430\u043d\u0430 \u0418\u0432\u0430\u043d\u043e\u0432\u043d\u0430",
              login: "KERBER-SI",
              birthDate: "1984-07-27",
              rb: 1,
              sbs: 1,
              atd: 0,
              hire_date: null,
              dismissal_date: null,
              is_initialized: 1,
              email: "SIKERBER@SBERBANK.RU",
              jobcode:
                "10/\u0412\u041c \u041c\u041c\u0411/\u041f\u0440\u043e\u0434\u0422\u0438\u043f\u041f\u0440-\u0442\u043e\u0432/\u041c\u041c\u0411",
              short_jobcode: "\u0412\u041c \u041c\u041c\u0411",
              tb: 44,
              organization:
                "\u0423\u0420\u041c \u0441.\u0411\u043e\u0433\u0443\u0447\u0430\u043d\u044b",
              synonym:
                "\u0412\u0435\u0434\u0443\u0449\u0438\u0439 \u043c\u0435\u043d\u0435\u0434\u0436\u0435\u0440 \u043f\u043e \u0440\u0430\u0431\u043e\u0442\u0435 \u0441 \u043a\u043b\u0438\u0435\u043d\u0442\u0430\u043c\u0438 \u041c\u0411",
              avatar:
                "https://sberbank-school.ru/avatar/c8212ea4455d189d006020b059b8dfe4?width=180&height=180",
              sapid: "00279518",
              is_dismissed: false,
              created_at: "2014-05-22 08:25:44",
              updated_at: "2021-12-02 12:33:26",
              init_time: "2018-10-30 04:40:02",
              sf_type_of_employee:
                "\u041f\u043e\u0441\u0442\u043e\u044f\u043d.\u0440\u0430\u0431\u043e\u0442.(\u0448\u0442\u0430\u0442)",
              vspcode: null,
              tb_name:
                "\u0421\u0438\u0431\u0438\u0440\u0441\u043a\u0438\u0439 \u0431\u0430\u043d\u043a",
              gosb: "\u041a\u0440\u0430\u0441\u043d\u043e\u044f\u0440\u0441\u043a\u043e\u0435 \u043e\u0442\u0434\u0435\u043b\u0435\u043d\u0438\u0435 \u21168646",
              sf_status: 1,
              status: 0,
            },
          },
        ],
      },
    };
  },

  methods: {
    getPropertyData(attribute) {
      return this.userDataFull.included[this.userDataFull.included.length - 1].attributes[`${attribute}`] != null ?
        this.userDataFull.included[this.userDataFull.included.length - 1].attributes[`${attribute}`] : 
        " - ";
    },
    
    checkEmptyString(str) {
      return str != null ? str : " - ";
    },
  },
  computed: {},
};
</script>

<style scoped>
.data{
  width: 25%;
}
.description{
    width: auto;
    padding: 5px;
    font-weight: bold;
    word-wrap: normal;
}
.label{
    display: inline-block;
    padding: 0 0.545em;
    font-size: 85%;
    font-weight: 600;
    line-height: 1.818em;
    border-color: #818a91;
    background: #818a91;
    color: #fff;
}
span{
    margin-right: 5px;
    border-radius: 5px;
}
.label-danger{
    border-color: #e46050;
    background: #e46050;
    color: #fff;
}
.label-success{
    border-color: #78bd5d;
    background: #78bd5d;
    color: #fff;
}
</style>
