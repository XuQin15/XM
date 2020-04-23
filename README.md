No2.html
var num1 = prompt("请输入数字：");
	function isReverse(num) {
		var sNum = String(num).split('').reverse().join('') - 0;
		return sNum === num;
	}	
	console.log(isReverse(parseInt(num1)));
  
  
