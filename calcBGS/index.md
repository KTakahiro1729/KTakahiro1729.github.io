<script src="https://unpkg.com/vue"></script>

<div id='app'>


|検査項目|単位|正常値|計測値|解釈|
|:-------|---:|-----:|-----:|:--:|
|pH||{{min_ph}}~{{max_ph}}|<input class='form-control' type='number' v-model='val_ph'>|{{lh_ph}}|

<table>
  <tr>
    <th>検査項目</th>
    <th>単位</th>
    <th>正常値</th>
    <th>計測値</th>
    <th>解釈</th>
  </tr>
  <tr>
    <td>pH</td>
    <td></td>
    <td>{{min_ph}} ~ {{max_ph}}</td>
    <td><input class='form-control' type='number' v-model='val_ph'></td>
    <td>{{lh_ph}}</td>
  </tr>
</table>

</div>

<script>
const vm = new Vue({
 el: "#app",
 data: {min_ph: 7.35, max_ph:7.45, val_ph: 7.4},
 computed:{lh_ph: function(){
   if (this.val_ph < this.min_ph) {return "L";}
   if (this.max_ph < this.val_ph) {return "H";}
   return "";
    }},
  })
</script>

測定値をサーバーに送信したり、ブラウザに保存したりすることはありません。
不安な方は、Ctrl-sでこのページを保存した後、ご使用ください。