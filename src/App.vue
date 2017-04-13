<style>
    .date {
        display: inline-block;
        padding: 6px;
        line-height: 22px;
        font-size: 16px;
        border: 2px solid #fff;
        box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.2);
        border-radius: 2px;
        color: #5F5F5F;
    }
</style>
<template>
        <div id="app" style="text-align:center">
        <img src="./assets/logo.png">
        <div class="hello">
            <div>timepicker</div>
            <myDatepicker 
                :addClass="'date'" 
                :format="format" 
                :months="months" 
                :buttons="buttons" 
                :timepicker="true" 
                :min="'2017-04-12'"
                :disabled="disabled" 
                :sundayFirst="true">
            </myDatepicker>
            <br /><br /><br />
            <div>datepicker</div>
            <myDatepicker 
                :addClass="'date'" 
                :format="format">
            </myDatepicker>
        </div>
    </div>
</template>

<script>
    import myDatepicker from './datetimepicker.vue'
    export default {
        data: function () {
            return {
                init: '2017-04-20',
                format: 'YYYY-MM-DD HH:mm',
                weeks: ['一', '二', '三', '四', '五', '六', '日'],
                months: ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月', '10月', '11月', '12月'],
                buttons: {
                    ok: '确认',
                    cancel:'取消'
                },
                disabled: {
                    type: 'inWeek',
                    arr: [3, 4, 6, 7]
                }
            }
        },
        components: {
            myDatepicker
        }
    }

</script>