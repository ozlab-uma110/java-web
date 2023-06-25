# java-web

<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
    <label for="allcheck-chk-0"><input type="checkbox" name="allcheck-chk-0" id="allcheck-chk[]">GroupA</label>
	<div id="boxes-0">	
	  <label><input type="checkbox" name="chk-0" value="A">ChatGPT-4.0</label>
	  <label><input type="checkbox" name="chk-0" value="A">Machine Learning</label>
	  <label><input type="checkbox" name="chk-0" value="A">Deep Learning</label>
	  <label><input type="checkbox" name="chk-0" value="A">Deep Learning</label>
   	</div> 
   	
   	<label for="allcheck-chk-1"><input type="checkbox" name="allcheck-chk-1" id="allcheck-chk-1">GroupB</label>
	<div id="boxes-1">	
	  <label><input type="checkbox" name="chk-1" value="A">B-FactorA</label>
	  <label><input type="checkbox" name="chk-1" value="A">B-FactorB</label>
	  <label><input type="checkbox" name="chk-1" value="A">B-FactorC</label>
	  <label><input type="checkbox" name="chk-1" value="A">B-FactorD</label>
   	</div>
   	
   	<label for="allcheck-chk-2"><input type="checkbox" name="allcheck-chk-2" id="allcheck-chk-2">GroupC</label>
	<div id="boxes-2">	
	  <label><input type="checkbox" name="chk-2" value="A">C-FactorA</label>
	  <label><input type="checkbox" name="chk-2" value="A">C-FactorB</label>
	  <label><input type="checkbox" name="chk-2" value="A">C-FactorC</label>
	  <label><input type="checkbox" name="chk-2" value="A">C-FactorD</label>
   	</div>  
      

</body>

<script type="text/javascript">
  // タグ内にjavascriptコードを直接記述します。
  console.log("JavaScriptを実行しています");
  $(function() {
	  	const chk_num = 5;
	  	for(let i=0;i<chk_num;i++){
		    // 1. 「全選択」する
		    $("#allcheck-chk["+i+"]").on('click', function() {
		    	console.log("all");
		      $("input[name='chk["+i+"]']").prop('checked', this.checked);
		    });
		    // 2. 「全選択」以外のチェックボックスがクリックされたら、
		    $("input[name='chk["+i+"]']").on('click', function() {
		     console.log("a");
		      if ($('#boxes['+i+'] :checked').length == $('#boxes['+i+'] :input').length) {
		        // 全てのチェックボックスにチェックが入っていたら、「全選択」 = checked
		        console.log("b")
		        $('#allcheck-chk['+i+']').prop('checked', true);
		      } else {
		    	// 一つでもチェックボックスにチェックが入っていなかったら、「全選択」= no-checked
		        console.log("c")
		    	$('#allcheck-chk['+i+']').prop('checked', false);
		      }
		    });
	  	}
	  });
</script>

</html>
