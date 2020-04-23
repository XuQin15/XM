第一题
var arr1 = [0, 1, 2, 3, 4, 5];
	var arr2 = [0, 4, 6, 1, 3, 9];

	function getArrDifference(arr1, arr2) {
		return arr1.concat(arr2).filter(function(v, i, arr) {
			return arr.indexOf(v) === arr.lastIndexOf(v);
		});
	}
	console.log(getArrDifference(arr1, arr2));
第二题
var num1 = prompt("请输入数字：");
	function isReverse(num) {
		var sNum = String(num).split('').reverse().join('') - 0;
		return sNum === num;
	}	
	console.log(isReverse(parseInt(num1)));
	
第三题
function getStringLength(str) {
		var slength = 0;
		for(i = 0; i < str.length; i++) {
			if((str.charCodeAt(i) >= 0) && (str.charCodeAt(i) <= 255))
				slength = slength + 1;
			else
				slength = slength + 2;
		}
		return slength;
};
 
  
