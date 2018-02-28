<template>
  <div class="card">
    <div class="card-content">
      <div class="row sub-topic-pb">
        <div class="sub-topic">
          <div class="col-sm-6">
            <p-progress :value="60" type="warning"></p-progress>
          </div>
          <div class="col-sm-2">
            <h5>מושג הגבול</h5>
          </div>
          <div class="col-sm-1">
            <div class="icon-container" @click="notAvailable">
               <span class="ti-pencil-alt"> </span>
               <span class="icon-name">תרגל </span>
            </div>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
              <span class="ti-announcement"></span>
              <span class="icon-name">4 </span>
            </div>
          </div>
          <div class="col-sm-1 level">
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
          </div>
        </div>
        <div class="sub-topic">
          <div class="col-sm-6">
            <p-progress :value="90" type="success"></p-progress>
          </div>
          <div class="col-sm-2">
            <h5>  חקירת פונקציות</h5>
          </div>
          <div class="col-sm-1">
            <div class="icon-container" @click="notAvailable">
               <span class="ti-pencil-alt"> </span>
               <span class="icon-name" >תרגל </span>
            </div>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
              <span class="ti-announcement"></span>
              <span class="icon-name">10</span>
            </div>
          </div>
          <div class="col-sm-1 level">
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
          </div>
        </div>
        <div class="sub-topic">
          <div class="col-sm-6">
            <p-progress :value="20" type="danger"></p-progress>
          </div>
          <div class="col-sm-2">
            <h5> פונקציה קדומה</h5>
          </div>
          <div class="col-sm-1">
            <div class="icon-container" @click="notAvailable">
               <span class="ti-pencil-alt"> </span>
               <span class="icon-name">תרגל </span>
            </div>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
              <span class="ti-announcement"></span>
              <span class="icon-name">4 </span>
            </div>
          </div>
          <div class="col-sm-1 level">
            <span class="ti-star"></span>
          </div>
        </div>
        <div class="sub-topic">
          <div class="col-sm-6">
            <p-progress :value="100" type="success"></p-progress>
          </div>
          <div class="col-sm-2">
            <h5> טכניקה של נגזרות ושימושי משיק</h5>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
               <span class="ti-pencil-alt"> </span>
               <router-link :to="{name: 'תרגול'}">
                 <span class="icon-name">תרגל </span>
               </router-link>
            </div>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
             <span class="ti-announcement"></span>
             <span class="icon-name">2 </span>
            </div>
          </div>
          <div class="col-sm-1 level">
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
            <span class="ti-star"></span>
          </div>
        </div>
        <div class="sub-topic">
          <div class="col-sm-6">
            <p-progress :value="20" type="danger"></p-progress>
          </div>
          <div class="col-sm-2">
            <h5> בעיות קיצון</h5>
          </div>
          <div class="col-sm-1">
            <div class="icon-container" @click="notAvailable">
               <span class="ti-pencil-alt"> </span>
               <span class="icon-name">תרגל </span>
            </div>
          </div>
          <div class="col-sm-1">
            <div class="icon-container">
             <span class="ti-announcement"> </span>
            </div>
          </div>
          <div class="col-sm-1 level">
            <span class="ti-star"></span>
          </div>
        </div>
        <div class="icon-container random">
           <span class="ti-hand-open"> </span>
           <span class="icon-name"> הגרל שאלה </span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import {DatePicker, TimeSelect, Slider, Tag, Input, Button, Select, Option} from 'element-ui'
  import PProgress from 'src/components/UIComponents/Progress.vue'
  import PSwitch from 'src/components/UIComponents/Switch.vue'
  import swal from 'sweetalert2'

  export default {
    components: {
      [DatePicker.name]: DatePicker,
      [TimeSelect.name]: TimeSelect,
      [Slider.name]: Slider,
      [Tag.name]: Tag,
      [Input.name]: Input,
      [Button.name]: Button,
      [Option.name]: Option,
      [Select.name]: Select,
      PSwitch,
      PProgress
    },
    data () {
      return {
        enabledRadio: '2',
        disabledRadio: '2',
        switches: {
          defaultOn: true,
          defaultOff: false,
          plainOn: true,
          plainOff: false,
          withIconsOn: true,
          withIconsOff: false
        },
        sliders: {
          simple: 30,
          rangeSlider: [20, 50]
        },
        selects: {
          simple: '',
          countries: [{value: 'Bahasa Indonesia', label: 'Bahasa Indonesia'},
            {value: 'Bahasa Melayu', label: 'Bahasa Melayu'},
            {value: 'Català', label: 'Català'},
            {value: 'Dansk', label: 'Dansk'},
            {value: 'Deutsch', label: 'Deutsch'},
            {value: 'English', label: 'English'},
            {value: 'Español', label: 'Español'},
            {value: 'Eλληνικά', label: 'Eλληνικά'},
            {value: 'Français', label: 'Français'},
            {value: 'Italiano', label: 'Italiano'},
            {value: 'Magyar', label: 'Magyar'},
            {value: 'Nederlands', label: 'Nederlands'},
            {value: 'Norsk', label: 'Norsk'},
            {value: 'Polski', label: 'Polski'},
            {value: 'Português', label: 'Português'},
            {value: 'Suomi', label: 'Suomi'},
            {value: 'Svenska', label: 'Svenska'},
            {value: 'Türkçe', label: 'Türkçe'},
            {value: 'Íslenska', label: 'Íslenska'},
            {value: 'Čeština', label: 'Čeština'},
            {value: 'Русский', label: 'Русский'},
            {value: 'ภาษาไทย', label: 'ภาษาไทย'},
            {value: '中文 (简体)', label: '中文 (简体)'},
            {value: 'W">中文 (繁體)', label: 'W">中文 (繁體)'},
            {value: '日本語', label: '日本語'},
            {value: '한국어', label: '한국어'}],
          multiple: 'ARS'
        },
        tags: {
          dynamicTags: ['Tag 1', 'Tag 2', 'Tag 3'],
          inputVisible: false,
          inputValue: ''
        },
        pickerOptions1: {
          shortcuts: [{
            text: 'Today',
            onClick (picker) {
              picker.$emit('pick', new Date())
            }
          },
          {
            text: 'Yesterday',
            onClick (picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24)
              picker.$emit('pick', date)
            }
          },
          {
            text: 'A week ago',
            onClick (picker) {
              const date = new Date()
              date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
              picker.$emit('pick', date)
            }
          }]
        },
        datePicker: '',
        dateTimePicker: '',
        timePicker: ''
      }
    },
    methods: {
      notAvailable() {
        swal({
            title: `תת נושא לא פעיל`,
            text: 'אנא בחר בתרגול תת הנושא טכניקה של נגזרות ושימושי משיק',
            buttonsStyling: false,
            confirmButtonText: 'אישור',
            confirmButtonClass: 'btn btn-success btn-fill'
          })
      },
      handleClose (tag) {
        this.tags.dynamicTags.splice(this.tags.dynamicTags.indexOf(tag), 1)
      },

      showInput () {
        this.tags.inputVisible = true
        this.$nextTick(() => {
          this.$refs.saveTagInput.$refs.input.focus()
        })
      },

      handleInputConfirm () {
        let inputValue = this.tags.inputValue
        if (inputValue) {
          this.tags.dynamicTags.push(inputValue)
        }
        this.tags.inputVisible = false
        this.tags.inputValue = ''
      }
    }
  }
</script>
<style>
  .extended-forms .el-select {
    width: 100%;
    margin-bottom: 30px;
  }
</style>
