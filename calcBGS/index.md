<script src="https://unpkg.com/vue"></script>

<div id='app' markdown='1'>

|検査項目|単位|正常値|計測値|解釈|
|:-------|---:|-----:|-----:|:--:|
|pH||{{min_ph}}~{{max_ph}}|<input class='form-control' type='number' v-model='val_ph'>|{{lh_ph}}|

</div>

<script>
const vm = new Vue({
 el: "#app",
 data: {val_ph: 7.4},
 computed:{lh_ph: function(){
   if (this.val_ph < this.min_ph) {return "L";}
   if (this.max_ph < this.val_ph) {return "H";}
   return "";
    }},
  })
</script>

測定値をサーバーに送信したり、ブラウザに保存したりすることはありません。
不安な方は、Ctrl-sでこのページを保存した後、ご使用ください。