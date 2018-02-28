<template>
  <div class="community" dir="rtl">
    <time-line v-if="exerciseNumber === 1" type="simple">
      <time-line-item class="timeline-inverted" badge-type="info" badgeIcon="ti-help">
        <span slot="header" class="label label-info"> נועם</span>
        <p slot="body" style="text-align:right">
  אני לא זוכרת מה הנוסחא לגזירה של נעלם ריבועי, מישהו יכול לעזור?
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 10 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>
      <time-line-item class="timeline-inverted" badge-type="success" badgeIcon="ti-check-box">
        <span slot="header" class="label label-success">
          <i class="ti-cup"></i> עדן</span>
        <p slot="body" style="text-align:right">
          <img src="static/img/solutions/comm1.png"></img>
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 35 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>

    </time-line>
    <time-line v-if="exerciseNumber === 2" type="simple">
      <time-line-item class="timeline-inverted" badge-type="info" badgeIcon="ti-help">
        <span slot="header" class="label label-info"> ליטל</span>
        <p slot="body" style="text-align:right">
  מישהו יכול להסביר לי במלל את כללי הגזירה שעשו בהם שימוש בתרגיל?
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 10 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>
      <time-line-item class="timeline-inverted" badge-type="success" badgeIcon="ti-check-box">
        <span slot="header" class="label label-success">
          <i class="ti-cup"></i> עדן</span>
        <p slot="body" style="text-align:right">
          <img src="static/img/solutions/comm2.png"></img>
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 35 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>

    </time-line>
    <time-line v-if="exerciseNumber === 3 " type="simple">
      <time-line-item class="timeline-inverted" badge-type="info" badgeIcon="ti-help">
        <span slot="header" class="label label-info"><i class="ti-info-alt"></i> </span>
        <p slot="body" style="text-align:right">
    עוד אין פעילות בקהילה עבור שאלה זו. אהיה הראשון להוסיף שאלה
        <h6 slot="footer">
        </h6>
      </time-line-item>

    </time-line>
    <time-line v-if="exerciseNumber === 4" type="simple">
        <time-line-item class="timeline-inverted" badge-type="info" badgeIcon="ti-help">
        <span slot="header" class="label label-info"> אפק</span>
        <p slot="body" style="text-align:right">
  הגעתי לתשובה הסופית הנכונה אבל אני לא סגור על הדרך - מישהו יכול לעלות את הפתרון שלו?
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 10 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>

      <time-line-item class="timeline-inverted" badge-type="success" badgeIcon="ti-check-box">
        <span slot="header" class="label label-success"><i class="ti-cup"></i> עומרי</span></span>
        <p slot="body">
            בבקשה<br>
          <img src="static/img/solutions/comm4.png" ></img>
          <br>
        <h6 slot="footer">
          <i class="ti-time"></i>
          Yesterday at 5PM <br><br>
          <i class="ti-thumb-up"></i> 8 <i class="ti-thumb-down"></i> 
        </h6>
      </time-line-item>

      <time-line-item class="timeline-inverted" badge-type="danger" badgeIcon="ti-comment">
        <span slot="header" class="label label-danger">רועי</span>
        <p slot="body">
          התשובה הנכונה היא: <br>
          F'(X) = -3X -2
          <br>
          <br>
        <h6 slot="footer">
          <i class="ti-time"></i>
          Yesterday at 5PM <br><br>
          <i class="ti-thumb-up"></i> -1 <i class="ti-thumb-down"></i> 
        </h6>
      </time-line-item>
    </time-line>
    <time-line v-if="exerciseNumber === 5" type="simple">
      <time-line-item class="timeline-inverted" badge-type="info" badgeIcon="ti-help">
        <span slot="header" class="label label-info"> שלומי</span>
        <p slot="body" style="text-align:right">
  הסתבכתי קצת בחלק הראשון של השאלה, מישהו יכול להסביר לי את לוגיקת הפתרון?
        <h6 slot="footer">
          <i class="ti-time"></i>
          11 hours ago <br><br>
          <i class="ti-thumb-up"></i> 3 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>
      <time-line-item class="timeline-inverted" badge-type="success" badgeIcon="ti-check-box">
        <span slot="header" class="label label-success">
          <i class="ti-cup"></i> עדן</span>
        <p slot="body" style="text-align:right">
           נתון בתרגיל שהשיפוע אשר משיק לפונקציה בנקודה שבה <br> x=1 ו- y=6 <br> הוא -6.
          שלבי הפתרון:<br>
          <ul>
<li>ראשית יש לגזור את הפונקציה בהתאם לכללי נגזרת של מנה</li>

<li>	לאחר מכן יש להציב את הפרמטרים x=1 ו- y=6 בנגזרת הראשונה של הפונקציה</li>
<li>	לאחר צמצום נמצא את הפרמטרים a ו-b</li>
<li>נציב את הפרמטרים שהתקבלו במשוואת המשיק ונקבל את התשובה</li>
</ul>
        <h6 slot="footer">
          <i class="ti-time"></i>
          1 hours ago <br><br>
          <i class="ti-thumb-up"></i> 12 <i class="ti-thumb-down"></i>   
        </h6>

      </time-line-item>

    </time-line>
  </div>
</template>

<script>
import TimeLineItem from '../Dashboard/Stats/TimeLineItem.vue'
import TimeLine from '../Dashboard/Stats/TimeLine.vue'

export default {
  components: {
    TimeLineItem,
    TimeLine
  },
  props: ['exerciseNumber']
}
</script>
