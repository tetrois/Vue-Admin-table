<template>
  <div>
    <hr />
    <div class="el-tabs el-tabs--top el-tabs--border-card">
      <div class="el-tabs__content">
        <div class="el-tab-pane">
          <!-- Buttons -->
          <div
            style="
              display: flex;
              justify-content: flex-end;
              margin-bottom: 20px;
            "
          >
            <a
              target="_blank"
              href="/admin/users/49/impersonate"
              style="display: block; margin-right: 10px"
            >
              <button type="button" class="el-button el-button--default">
                <span> Авторизоваться </span>
              </button>
            </a>

            <a
              target="_blank"
              href="/admin/testing/users/49/event-user-updated"
              style="display: block; margin-right: 10px"
            >
              <button
                type="button"
                class="el-button el-button--default"
                title="Выполнить автоназначения траекторий. Команда https://rb.sberbank-school.ru/admin/testing/users/49/event-user-updated"
              >
                <span> Выполнить автоназначения </span>
              </button>
            </a>
            <a
              href="/admin/users/49/assigntrajectory"
              style="display: block; margin-right: 10px"
            >
              <button type="button" class="el-button el-button--default">
                <span> Добавить траекторию </span>
              </button>
            </a>
            <button
              id="admin_deleteCourses"
              type="button"
              class="el-button el-button--default"
            >
              <span> Удалить выбранные траектории </span>
            </button>
          </div>

            <!-- Table -->
          <div class="el-row">
            <div class="el-loading-mask" style="display: none">
              <div class="el-loading-spinner">
                <svg viewBox="25 25 50 50" class="circular">
                  <circle cx="50" cy="50" r="20" fill="none" class="path"></circle>
                </svg>
                <!---->
              </div>
            </div>
            <!-- Шапка таблицы -->
            <div class="el-table el-table--fit el-table--striped el-table--border el-table--scrollable-x">
              <div class="el-table__body-wrapper">
                <table cellspacing="0" cellpadding="0" border="0" class="el-table__body" style="width: auto">
                  <colgroup>
                    <col name="el-table_3_column_1" width="auto" />
                    <col name="el-table_3_column_2" width="50" />
                    <col name="el-table_3_column_3" width="100" />
                    <col name="el-table_3_column_4" width="100" />
                    <col name="el-table_3_column_5" width="100" />
                    <col name="el-table_3_column_6" width="140" />
                    <col name="el-table_3_column_7" width="80" />
                    <col name="el-table_3_column_8" width="100" />
                    <col name="el-table_3_column_9" width="65" />
                    <col name="el-table_3_column_10" width="20" />
                  </colgroup>
                  <tbody class="data-courses">
                    <tr class="">
                      <th colspan="1" rowspan="1" class="el-table_3_column_1">
                        <div class="cell">
                          Название траектории
                          <label onclick="checkJCAll()" class="label label-success label-outline" style="margin: 0 0 0 auto; position: relative">
                            <i class="fa fa-check" aria-hidden="true"> </i>
                            Check All JC
                          </label>
                        </div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_2">
                        <div class="cell">Статус</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_3">
                        <div class="cell">Дата КМ</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_4">
                        <div class="cell">Дата SF</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_5">
                        <div class="cell">Ответ SF</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_6">
                        <div class="cell">Тип назначения</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_7">
                        <div class="cell">Прогресс (%)</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_8">
                        <div class="cell">Дата ВШР</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_9">
                        <div class="cell">Доп.</div>
                      </th>
                      <th colspan="1" rowspan="1" class="el-table_3_column_10">
                        <div class="cell"></div>
                      </th>
                    </tr>

                    <tr class="el-table__row class-for-remove" style="background-color: rgba(253, 201, 201, 0.43)">
                      <td class="el-table__cell">
                        <div class="cell">
                          <div class="pointer">
                            <a title="Детальная информация">Руководители Клиентский менеджер</a>
                          </div>
                          <div class="helper">
                            <span onclick="copyCourseName(this)" class="label label-warning">Copy</span>&nbsp;
                            <span
                              onclick="checkJCODEs(this)"
                              class="label label-default"
                              title="Индикатор, есть ли текущий ДжКод в списке автоназначений у данного курса. Если красный - нет, если зеленый - есть."
                              >JCode</span
                            >&nbsp;
                          </div>
                        </div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell">
                          <span>
                            <span class="el-popover__reference-wrapper">
                              <div
                                class="name-wrapper el-popover__reference"
                                aria-describedby="el-popover-4328"
                                tabindex="0"
                                style="cursor: pointer"
                                onmouseover="document.querySelector('#el-popover-0').style.display = 'inline-block';"
                                onmouseout="document.querySelector('#el-popover-0').style.display = 'none';"
                              >
                                <a
                                  target="_blank"
                                  href="/admin/trajectories/42/users/14"
                                >
                                  <label
                                    class="label label-default label-outline"
                                  >
                                    <i class="fa fa-trash" aria-hidden="true">
                                    </i>
                                    42
                                  </label>
                                </a>

                                <div
                                  role="tooltip"
                                  id="el-popover-0"
                                  aria-hidden="true"
                                  class="el-popover el-popper"
                                  tabindex="0"
                                  style="
                                    position: absolute;
                                    transform-origin: right center;
                                    z-index: 99999;
                                    display: none;
                                    width: max-content;
                                  "
                                >
                                  <!---->
                                  <p><b>Тип назначения:</b> admin</p>
                                  <p>
                                    <b>Дата назначения:</b>
                                    2018-03-13 09:37:14
                                  </p>
                                  <p>
                                    <b>Обновление назначения:</b>
                                    2019-04-18 17:34:13
                                  </p>

                                  <p>
                                    <b>Дата удаления:</b>
                                    2018-03-13 09:38:04
                                  </p>

                                  <p>
                                    <b>Текущая траектория:</b>
                                    0
                                  </p>
                                  <p>
                                    <b>Посещалась ли траектория:</b>
                                    false
                                  </p>

                                  <p>
                                    <b>Наличие конфликтов:</b>
                                    0
                                  </p>
                                  <p>
                                    <b>Режим назначения:</b>
                                    Обучение
                                  </p>
                                  <div x-arrow="" class="popper__arrow" style="top: 342px"></div>
                                </div>
                              </div>
                            </span>
                          </span>
                        </div>
                      </td>
                      <td rowspan="1" colspan="1" class="el-table_2_column_3">
                        <div class="cell">-</div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell">-</div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell"></div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell">Обучение</div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell">0</div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell">-</div>
                      </td>
                      <td class="el-table__cell">
                        <div style="text-align: center">
                          <a onclick="copyAnswers(this, 0)" class="helper-a" style="background-color: #c377e0"></a>
                          <a onclick="copyAnswers(this, 1)" class="helper-a" style="background-color: #51e898" title="Ответ: Траектория назначена на ознакомление"></a>
                          <a onclick="copyAnswers(this, 2)" class="helper-a" style="background-color: #0079bf"></a>
                        </div>
                      </td>
                      <td class="el-table__cell">
                        <div class="cell"></div>
                      </td>
                    </tr>
                  </tbody>
                </table>
                <div class="el-table__empty-block" style="height: 100%; width: 1366px">
                  <span class="el-table__empty-text">Данные отсутствуют.</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.el-tabs--border-card {
  background: #ffffff;
}
.el-tabs--border-card > .el-tabs__content {
  padding: 15px;
}
.el-tabs {
  overflow: auto;
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-end;
}

.el-button {
  display: inline-block;
  line-height: 1;
  white-space: nowrap;
  cursor: pointer;
  background: #ffffff;
  border: 1px solid #dcdfe6;
  border-color: #dcdfe6;
  color: #606266;
  -webkit-appearance: none;
  text-align: center;
  box-sizing: border-box;
  outline: none;
  margin: 0;
  transition: 0.1s;
  font-weight: 500;
  padding: 12px 20px;
  font-size: 14px;
  border-radius: 4px;
}
</style>



<style scoped>
.el-loading-mask {
    position: absolute;
    z-index: 2000;
    background-color: rgba(255, 255, 255, 0.9);
    margin: 0;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    transition: opacity 0.3s;
}
.el-row {
    position: relative;
    box-sizing: border-box;
}
.el-table--border {
    border-right: none;
    border-bottom: none;
}
.el-table--group, .el-table--border {
    border: 1px solid #EBEEF5;
}
.el-table {
    position: relative;
    overflow: hidden;
    box-sizing: border-box;
    flex: 1;
    width: 100%;
    max-width: 100%;
    background-color: #FFFFFF;
    font-size: 14px;
    color: #606266;
}
.el-table--scrollable-x .el-table__body-wrapper {
    overflow-x: auto;
}
.el-table__body-wrapper {
    overflow: hidden;
    position: relative;
}
.el-table__header-wrapper, .el-table__body-wrapper, .el-table__footer-wrapper {
    width: 100%;
}
table {
    background-color: transparent;
    border-spacing: 0;    
}
.el-table tr {
    background-color: #FFFFFF;
}
tr {
    display: table-row;
    vertical-align: inherit;
    border-color: inherit;
}
th {
    text-align: left;
}
td, th {
    padding: 0;
}
.el-table .cell {
    box-sizing: border-box;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: normal;
    word-break: break-all;
    line-height: 23px;
    padding-left: 10px;
    padding-right: 10px;
}
.helper-admin .cell {
    display: flex;
}
.el-table th.el-table__cell.is-leaf, .el-table td.el-table__cell {
    border-bottom: 1px solid #EBEEF5;
}
.el-table--border .el-table__cell {
    border-right: 1px solid #EBEEF5;
}
.el-table .el-table__cell {
    padding: 12px 0;
    min-width: 0;
    box-sizing: border-box;
    text-overflow: ellipsis;
    vertical-align: middle;
    position: relative;
    text-align: left;
}
.el-table__empty-text {
    line-height: 60px;
    width: 50%;
    color: #909399;
}
.el-table__empty-block {
    min-height: 60px;
    text-align: center;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>