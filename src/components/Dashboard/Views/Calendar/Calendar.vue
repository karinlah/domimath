<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-10 col-md-offset-1">
        <div class="card card-calendar">
          <div class="card-content">
            <div id="fullCalendar"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import swal from 'sweetalert2'
  import $ from 'jquery'
  import 'fullcalendar'

  var today = new Date()
  var y = today.getFullYear()
  var m = today.getMonth()
  var d = today.getDate()
  export default {
    data () {
      return {
        events: [
          {
            title: 'טיול שנתי',
            start: new Date(y, m, d),
            end: new Date(y, m, d + 1),
            className: 'event-default'
          },
          {
            id: 999,
            title: 'שיעור כיתתי',
            start: new Date(y, m, d - 1, 6, 0),
            allDay: false,
            className: 'event-rose'
          },
          {
            title: 'שיעור כיתתי',
            start: new Date(y, m, d + 3, 10, 0),
            allDay: false,
            className: 'event-green'
          },
          {
            title: 'שיעור כיתתי',
            start: new Date(y, m, d + 5, 15, 0),
            allDay: false,
            className: 'event-green'
          },
          {
            title: 'שיעור כיתתי',
            start: new Date(y, m, d + 1, 13, 0),
            allDay: false,
            className: 'event-green'
          },
          {
            title: 'הקבצה טריגו',
            start: new Date(y, m, d + 2, 11, 0),
            allDay: false,
            className: 'event-red'
          },
          {
            title: 'הקבצה אלגברה',
            start: new Date(y, m, d + 1, 17, 0),
            allDay: false,
            className: 'event-red'
          },
          {
            title: ' הקבצה חדו״א',
            start: new Date(y, m, d + 6, 9, 0),
            allDay: false,
            className: 'event-red'
          },
          {
            title: ' הקבצה גיאומטריה אנליטית ',
            start: new Date(y, m, d + 4, 12, 0),
            allDay: false,
            className: 'event-red'
          },
        ]
      }
    },
    methods: {
      initCalendar ($) {
        var self = this
        var $calendar = $('#fullCalendar')
        $calendar.fullCalendar({
          header: {
            left: 'title',
            center: 'month,agendaWeek,agendaDay',
            right: 'prev,next,today'
          },
          defaultView: 'agendaWeek',
          defaultDate: today,
          selectable: true,
          selectHelper: true,
          views: {
            month: { // name of view
              titleFormat: 'MMMM YYYY'
              // other view-specific options here
            },
            week: {
              titleFormat: ' MMMM D YYYY'
            },
            day: {
              titleFormat: 'D MMM, YYYY'
            }
          },
          eventClick: function(calEvent, jsEvent, view) {
            swal({
              title: 'תרגול מותאם',
              confirmButtonText: 'אישור',
              buttonsStyling: false,
              confirmButtonClass: 'btn btn-success',
              showCancelButton: false,
              html: 'התרגול יהיה על תרגילים 13-62 מעמוד 43. <br> <b> תתרגל יחד עם שלומי מורן ואבי </b> '+
              '<br><img src="../../static/img/tables/group.jpg" style="width:37%"></img>'
            })
          },
          select: function (start, end) {
            // on select we show the Sweet Alert modal with an input
            swal({
              title: 'צור אירוע חדש',
              html: '<div class="form-group">' +
              '<input class="form-control" placeholder="שם האירוע" id="input-field">' +
              '</div>',
              showCancelButton: true,
              confirmButtonClass: 'btn btn-success',
              cancelButtonClass: 'btn btn-danger',
              buttonsStyling: false
            }).then(function (result) {
              var eventData
              var eventTitle = $('#input-field').val()
              if (eventTitle) {
                eventData = {
                  title: eventTitle,
                  start: start,
                  end: end
                }
                $calendar.fullCalendar('renderEvent', eventData, true) // stick? = true
              }
              $calendar.fullCalendar('unselect')
            })
          },
          editable: true,
          eventLimit: true, // allow "more" link when too many events

          // color classes: [ event-blue | event-azure | event-green | event-orange | event-red ]
          events: self.events
        })
      }
    },
    mounted () {
      window.$ = window.jQuery = $
      this.initCalendar($)
    }
  }
</script>
<style>
  #fullCalendar {
    min-height: 300px;
  }

  .el-loading-spinner .path {
    stroke: #66615B !important;
  }
</style>
