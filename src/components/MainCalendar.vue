<template>
  <div class="calendar-wrap">
    <table class="calendar">
      <thead>
        <tr>
          <th class="day-title" scope="col">Sun</th>
          <th class="day-title" scope="col">Mon</th>
          <th class="day-title" scope="col">Tue</th>
          <th class="day-title" scope="col">Wed</th>
          <th class="day-title" scope="col">Thu</th>
          <th class="day-title" scope="col">Fri</th>
          <th class="day-title" scope="col">Sat</th>
        </tr>
      </thead>
      <tbody>
        <tr class="week">
          <!-- <td class="day prev-mon" tabindex="0"><span class="day-number">29</span></td>
          <td class="day prev-mon" tabindex="0"><span class="day-number">30</span></td>
          <td class="day prev-mon" tabindex="0"><span class="day-number">31</span></td> -->
          <td class="day today" tabindex="0"><span class="day-number">1</span></td>
          <td class="day" tabindex="0"><span class="day-number">2</span></td>
          <td class="day" tabindex="0"><span class="day-number">3</span></td>
          <td class="day" tabindex="0"><span class="day-number">4</span></td>
          <td class="day" tabindex="0"><span class="day-number">5</span></td>
          <td class="day" tabindex="0"><span class="day-number">6</span></td>
          <td class="day" tabindex="0"><span class="day-number">7</span></td>
        </tr>
        <tr class="week">
          <td class="day" tabindex="0"><span class="day-number">8</span></td>
          <td class="day" tabindex="0"><span class="day-number">9</span></td>
          <td class="day" tabindex="0"><span class="day-number">10</span></td>
          <td class="day" tabindex="0"><span class="day-number">11</span></td>
          <td class="day" tabindex="0"><span class="day-number">12</span></td>
          <td class="day" tabindex="0"><span class="day-number">13</span></td>
          <td class="day" tabindex="0"><span class="day-number">14</span></td>
        </tr>
        <tr class="week">
          <td class="day" tabindex="0"><span class="day-number">15</span></td>
          <td class="day" tabindex="0"><span class="day-number">16</span></td>
          <td class="day" tabindex="0"><span class="day-number">17</span></td>
          <td class="day" tabindex="0"><span class="day-number">18</span></td>
          <td class="day" tabindex="0"><span class="day-number">19</span></td>
          <td class="day" tabindex="0"><span class="day-number">20</span></td>
          <td class="day" tabindex="0"><span class="day-number">21</span></td>
        </tr>
        <tr class="week">
          <td class="day" tabindex="0"><span class="day-number">22</span></td>
          <td class="day" tabindex="0"><span class="day-number">23</span></td>
          <td class="day" tabindex="0"><span class="day-number">24</span></td>
          <td class="day" tabindex="0"><span class="day-number">25</span></td>
          <td class="day" tabindex="0"><span class="day-number">26</span></td>
          <td class="day" tabindex="0"><span class="day-number">27</span></td>
          <td class="day" tabindex="0"><span class="day-number">28</span></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: 'MainCalendar',
}
</script>
<style></style>
