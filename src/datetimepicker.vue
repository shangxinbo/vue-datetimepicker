<style scoped>
    .datepicker-overlay {
        position: fixed;
        width: 100%;
        height: 100%;
        z-index: 998;
        top: 0;
        left: 0;
        overflow: hidden;
        background: rgba(0, 0, 0, 0.5);
        -webkit-animation: fadein 0.5s;
        -moz-animation: fadein 0.5s;
        -ms-animation: fadein 0.5s;
        -o-animation: fadein 0.5s;
        animation: fadein 0.5s;
    }
    
    @keyframes fadein {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    @-moz-keyframes fadein {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    @-webkit-keyframes fadein {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    @-ms-keyframes fadein {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    @-o-keyframes fadein {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
    
    .cov-date-body {
        display: inline-block;
        background: #3F51B5;
        overflow: hidden;
        position: relative;
        font-size: 16px;
        font-family: 'Roboto';
        font-weight: 400;
        position: fixed;
        display: block;
        width: 400px;
        max-width: 100%;
        z-index: 999;
        top: 50%;
        left: 50%;
        -webkit-transform: translate(-50%, -50%);
        -ms-transform: translate(-50%, -50%);
        transform: translate(-50%, -50%);
        box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.2);
    }
    
    .cov-picker-box {
        background: #fff;
        width: 100%;
        display: inline-block;
        padding: 25px;
        box-sizing: border-box !important;
        -moz-box-sizing: border-box !important;
        -webkit-box-sizing: border-box !important;
        -ms-box-sizing: border-box !important;
        width: 400px;
        max-width: 100%;
        height: 280px;
        text-align: start!important;
    }
    
    .cov-picker-box td {
        height: 34px;
        width: 34px;
        padding: 0;
        line-height: 34px;
        color: #000;
        background: #fff;
        text-align: center;
        cursor: pointer;
    }
    
    .cov-picker-box td:hover {
        background: #E6E6E6;
    }
    
    table {
        border-collapse: collapse;
        border-spacing: 0;
        width: 100%;
    }
    
    .day {
        width: 14.2857143%;
        display: inline-block;
        text-align: center;
        cursor: pointer;
        height: 34px;
        padding: 0;
        line-height: 34px;
        color: #000;
        background: #fff;
        vertical-align: middle;
    }
    
    .week ul {
        margin: 0 0 8px;
        padding: 0;
        list-style: none;
    }
    
    .week ul li {
        width: 14.2%;
        display: inline-block;
        text-align: center;
        background: transparent;
        color: #000;
        font-weight: bold;
    }
    
    .passive-day {
        color: #bbb;
    }
    
    .checked {
        background: #F50057;
        color: #FFF !important;
        border-radius: 3px;
    }
    
    .unavailable {
        color: #ccc;
        cursor: not-allowed;
    }
    
    .cov-date-monthly {
        height: 150px;
    }
    
    .cov-date-monthly>div {
        display: inline-block;
        padding: 0;
        margin: 0;
        vertical-align: middle;
        color: #fff;
        height: 150px;
        float: left;
        text-align: center;
        cursor: pointer;
    }
    
    .cov-date-previous,
    .cov-date-next {
        position: relative;
        width: 20% !important;
        text-indent: -300px;
        overflow: hidden;
        color: #fff;
    }
    
    .cov-date-caption {
        width: 60%;
        padding: 50px 0!important;
        box-sizing: border-box;
        font-size: 24px;
    }
    
    .cov-date-caption span:hover {
        color: rgba(255, 255, 255, 0.7);
    }
    
    .cov-date-previous:hover,
    .cov-date-next:hover {
        background: rgba(255, 255, 255, 0.1);
    }
    
    .day:hover {
        background: #EAEAEA;
    }
    
    .unavailable:hover {
        background: none;
    }
    
    .checked:hover {
        background: #FF4F8E;
    }
    
    .cov-date-next::before,
    .cov-date-previous::before {
        width: 20px;
        height: 2px;
        text-align: center;
        position: absolute;
        background: #fff;
        top: 50%;
        margin-top: -7px;
        margin-left: -7px;
        left: 50%;
        line-height: 0;
        content: '';
        -webkit-transform: rotate(45deg);
        -moz-transform: rotate(45deg);
        transform: rotate(45deg);
    }
    
    .cov-date-next::after,
    .cov-date-previous::after {
        width: 20px;
        height: 2px;
        text-align: center;
        position: absolute;
        background: #fff;
        margin-top: 6px;
        margin-left: -7px;
        top: 50%;
        left: 50%;
        line-height: 0;
        content: '';
        -webkit-transform: rotate(-45deg);
        -moz-transform: rotate(-45deg);
        transform: rotate(-45deg);
    }
    
    .cov-date-previous::after {
        -webkit-transform: rotate(45deg);
        -moz-transform: rotate(45deg);
        transform: rotate(45deg);
    }
    
    .cov-date-previous::before {
        -webkit-transform: rotate(-45deg);
        -moz-transform: rotate(-45deg);
        transform: rotate(-45deg);
    }
    
    .date-item {
        text-align: center;
        font-size: 20px;
        padding: 10px 0;
        cursor: pointer;
    }
    
    .date-item:hover {
        background: #e0e0e0;
    }
    
    .date-list {
        overflow: auto;
        vertical-align: top;
        padding: 0;
    }
    
    .cov-vue-date {
        display: inline-block;
        color: #5D5D5D;
    }
    
    .button-box {
        background: #fff;
        vertical-align: top;
        height: 50px;
        line-height: 50px;
        text-align: right;
        padding-right: 20px;
    }
    
    .button-box span {
        cursor: pointer;
        padding: 10px 20px;
    }
    
    .watch-box {
        height: 100%;
        overflow: hidden;
    }
    
    .hour-box,
    .min-box {
        display: inline-block;
        width: 50%;
        text-align: center;
        height: 100%;
        overflow: auto;
        float: left;
    }
    
    .hour-box ul,
    .min-box ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
    
    .hour-item,
    .min-item {
        padding: 10px;
        font-size: 36px;
        cursor: pointer;
    }
    
    .hour-item:hover,
    .min-item:hover {
        background: #E3E3E3;
    }
    
    .hour-box .active,
    .min-box .active {
        background: #F50057;
        color: #FFF !important;
    }
    
     ::-webkit-scrollbar {
        width: 2px;
    }
    
     ::-webkit-scrollbar-track {
        background: #E3E3E3;
    }
    
     ::-webkit-scrollbar-thumb {
        background: #C1C1C1;
        border-radius: 2px;
    }
</style>
<template>
    <div class="cov-vue-date">
        <div class="datepickbox">
            <input type="text" class="cov-datepicker" readonly="readonly" :placeholder="placeholder" v-model="val" @click="showCheck" @foucus="showCheck" :class="addClass" />
        </div>
        <div class="datepicker-overlay" v-if="show">
            <div class="cov-date-body" :style="{'background-color':colors&&colors.header}">
                <div class="cov-date-monthly">
                    <div class="cov-date-previous" @click="nextMonth('pre')">«</div>
                    <div class="cov-date-caption" :style="{'color':colors&&colors.headerText}">
                        <span @click="showYear">
                            <small>{{checked.year}}</small>
                        </span>
                        <br>
                        <span @click="showMonth">{{displayMonth}}</span>
                    </div>
                    <div class="cov-date-next" @click="nextMonth('next')">»</div>
                </div>
                <div class="cov-date-box" v-if="layer=='day'">
                    <div class="cov-picker-box">
                        <div class="week">
                            <ul>
                                <li v-for="week in weeks">{{week}}</li>
                            </ul>
                        </div>
                        <div class="day" v-for="day in dayList" @click="checkDay(day)" :class="{'checked':day.checked,'unavailable':day.unavailable,'passive-day': !(day.inMonth)}"
                            :style="day.checked?{background:colors&&colors.checkedDate}:{}">{{day.value}}</div>
                    </div>
                </div>
                <div class="cov-date-box list-box" v-if="layer=='year'">
                    <div class="cov-picker-box date-list" id="yearList">
                        <div class="date-item" v-for="yearItem in years" @click="setYear(yearItem)">{{yearItem}}</div>
                    </div>
                </div>
                <div class="cov-date-box list-box" v-if="layer=='month'">
                    <div class="cov-picker-box date-list">
                        <div class="date-item" v-for="monthItem in months" @click="setMonth(monthItem)">{{monthItem}}</div>
                    </div>
                </div>
                <div class="cov-date-box list-box" v-if="layer=='hour'">
                    <div class="cov-picker-box date-list">
                        <div class="watch-box">
                            <div class="hour-box">
                                <div class="mui-pciker-rule mui-pciker-rule-ft"></div>
                                <ul>
                                    <li class="hour-item" v-for="hitem in hours" @click="setTime('hour', hitem, hours)" :class="{'active':hitem.checked}">{{hitem.value}}</li>
                                </ul>
                            </div>
                            <div class="min-box">
                                <div class="mui-pciker-rule mui-pciker-rule-ft"></div>
                                <div class="min-item" v-for="mitem in mins" @click="setTime('min',mitem, mins)" :class="{'active':mitem.checked}">{{mitem.value}}</div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="button-box">
                    <span @click="show=false">{{buttons.cancel}}</span>
                    <span @click="picked">{{buttons.ok}}</span>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import moment from 'moment'
    export default {
        props: {
            init: {
                type: String,
            },
            colors: {
                type: Object
            },
            addClass: {
                type: String
            },
            placeholder: {
                type: String
            },
            weeks: {
                type: Array,
                default() {
                    return this.$options.propsData.sundayFirst?['Su','Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa']:['Mo', 'Tu', 'We', 'Th', 'Fr', 'Sa', 'Su']
                }
            },
            months: {
                type: Array,
                default() {
                    return ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December']
                }
            },
            buttons: {
                type: Object,
                default() {
                    return {
                        ok: 'OK',
                        cancel: 'Cancel'
                    }
                }
            },
            timepicker: {
                type: Boolean,
                default: false
            },
            format: {
                type:String,
                default:'YYYY-MM-DD'
            },
            sundayFirst: {
                type:Boolean,
                default:false
            },
            min: {
                type: String
            },
            max: {
                type: String
            },
            disabled: {
                type: Object
            }
        },
        data() {
            let hours = () => {
                let list = []
                let hour = 24
                while (hour > 0) {
                    hour--
                    list.push({
                        checked: false,
                        value: hour < 10 ? '0' + hour : hour
                    })
                }
                return list
            }
            let mins = () => {
                let list = []
                let min = 60
                while (min > 0) {
                    min--
                    list.push({
                        checked: false,
                        value: min < 10 ? '0' + min : min
                    })
                }
                return list
            }
            return {
                hours: hours(),
                mins: mins(),
                val: this.init,
                show: false,
                layer: 'day',
                displayMonth: '',
                years: [],
                checked: {
                    oldtime: '',
                    currentMoment: null,
                    year: '',
                    month: '',
                    day: '',
                    hour: '00',
                    min: '00'
                },
                dayList: []
            }
        },
        methods: {
            showCheck() {
                if (this.val === '') {
                    this.showDay()
                } else {
                    this.checked.oldtime = this.val
                    this.showDay(this.val)
                }
                this.show = true
            },
            showDay(time) {
                let currentMoment
                if (time === undefined || !Date.parse(time)) {
                    currentMoment = moment()
                } else {

                    currentMoment = moment(time, this.format)
                }

                let days = []
                let firstDay = moment(currentMoment).date(1).day()   //当前月的第一天是星期几
                let previousMonth = moment(currentMoment).add(1, 'months')
                let nextMonth = moment(currentMoment).subtract(1, 'months')
                let monthDays = moment(currentMoment).daysInMonth()  //当前月有多少天
                let oldtime = this.checked.oldtime

                for (let i = 1; i <= monthDays; i++) {
                    days.push({
                        value: i,
                        inMonth: true,
                        unavailable: false,
                        checked: false,
                        moment: moment(currentMoment).date(i)
                    })
                    if (i === Math.ceil(moment(currentMoment).format('D'))
                        && moment(oldtime, this.format).year() === moment(currentMoment).year()
                        && moment(oldtime, this.format).month() === moment(currentMoment).month()) {
                        days[i - 1].checked = true
                    }
                }

                firstDay === 0 ? firstDay = 7 : firstDay

                for (let i = 0; i < firstDay - (this.SundayFirst ? 0 : 1); i++) {
                    let passiveDay = {
                        value: previousMonth.daysInMonth() - (i),
                        inMonth: false,
                        action: 'previous',
                        unavailable: false,
                        checked: false,
                        moment: moment(currentMoment).date(1).subtract(i + 1, 'days')
                    }
                    days.unshift(passiveDay)
                }
                var passiveDaysAtFinal = 42 - days.length
                for (let i = 1; i <= passiveDaysAtFinal; i++) {
                    let passiveDay = {
                        value: i,
                        inMonth: false,
                        action: 'next',
                        unavailable: false,
                        checked: false,
                        moment: moment(currentMoment).add(1, 'months').date(i)
                    }
                    days.push(passiveDay)
                }

                this.doDisabled(days)

                this.checked.currentMoment = currentMoment
                this.dayList = days
                this.checked.year = moment(currentMoment).format('YYYY')
                this.checked.month = moment(currentMoment).format('MM')
                this.checked.day = moment(currentMoment).format('DD')
                this.displayMonth = this.months[moment(currentMoment).month()]
                this.layer = 'day'
            },
            checkDay(obj) {
                if (obj.unavailable || obj.value === '') {
                    return false
                }
                if (!(obj.inMonth)) {
                    this.nextMonth(obj.action)
                }
                this.dayList.forEach((x) => {
                    x.checked = false
                })
                this.checked.day = this.pad(obj.value)
                obj.checked = true

                if (this.timepicker) {
                    this.layer = 'hour'
                    this.shiftActTime()
                }
            },
            nextMonth(type) {
                let next = null
                type === 'next' ? next = moment(this.checked.currentMoment).add(1, 'M') : next = moment(this.checked.currentMoment).add(-1, 'M')
                this.showDay(next)
            },
            pad(n) {
                n = Math.floor(n)
                return n < 10 ? '0' + n : n
            },
            doDisabled(days) {
                if (this.min || this.to) {
                    days.forEach((val, index) => {
                        if (this.min && val.moment.isBefore(this.min)) { //TODO 如果this max和format不同
                            val.unavailable = true
                        }
                        if (this.max && val.moment.isAfter(this.max)) { //TODO 如果this max和format不同
                            console.log(val.moment)
                            val.unavailable = true
                        }
                    })
                }
                if(this.disabled){
                    days.forEach((val,index)=>{
                        if(this.disabled.type=='inMonth'){
                           
                            if(this.disabled.arr.indexOf(val.moment.date())>=0){
                                val.unavailable = true
                            }
                        }
                        if(this.disabled.type=='inWeek'){
                            if(this.disabled.arr.indexOf(val.moment.day())>0){
                                val.unavailable = true
                            }
                        }
                    })
                }
            },
            showYear() {
                let year = moment(this.checked.currentMoment).year()
                this.years = []
                let yearTmp = []
                for (let i = year - 100; i < year + 5; ++i) {
                    yearTmp.push(i)
                }
                this.years = yearTmp
                this.layer = 'year'
                this.$nextTick(() => {
                    let listDom = document.getElementById('yearList')
                    listDom.scrollTop = (listDom.scrollHeight - 100)
                    listDom.addEventListener('scroll', (e) => {
                        if (listDom.scrollTop < listDom.scrollHeight - 100) {
                            let len = this.years.length
                            let lastYear = this.years[len - 1]
                            this.years.push(lastYear + 1)
                        }
                    }, false)
                })
            },
            showMonth() {
                this.layer = 'month'
            },
            setYear(year) {
                this.checked.currentMoment = moment(year + '-' + this.checked.month + '-' + this.checked.day)
                this.showDay(this.checked.currentMoment)
            },
            setMonth(month) {
                let mo = (this.months.indexOf(month) + 1)
                if (mo < 10) {
                    mo = '0' + '' + mo
                }
                this.checked.currentMoment = moment(this.checked.year + '-' + mo + '-' + this.checked.day)
                this.showDay(this.checked.currentMoment)
            },
            setTime(type, obj, list) {
                for (let item of list) {
                    item.checked = false
                    if (item.value === obj.value) {
                        item.checked = true
                        this.checked[type] = item.value
                    }
                }
            },
            picked() {
                let ctime = this.checked.year + '-' + this.checked.month + '-' + this.checked.day + ' ' + this.checked.hour + ':' + this.checked.min
                this.checked.currentMoment = moment(ctime, 'YYYY-MM-DD HH:mm')
                this.val = moment(this.checked.currentMoment).format(this.format)
                this.show = false
                this.$emit('change', this.val)
            },
            shiftActTime() {
                this.$nextTick(() => {
                    if (!document.querySelector('.hour-item.active')) {
                        return false
                    }
                    document.querySelector('.hour-box').scrollTop = (document.querySelector('.hour-item.active').offsetTop || 0) - 250
                    document.querySelector('.min-box').scrollTop = (document.querySelector('.min-item.active').offsetTop || 0) - 250
                })
            }
        }
    }

</script>