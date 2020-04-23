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
第八题

var timestamp = Date.parse(new Date());

 第九题
function PubSub() {
    this.handles = {
        eventName: {
            eventsList: [],
            isOne: false,
        }
    }
}
PubSub.prototype.subscribe = function (eventName, callback) {
    let EventsList = [];
    if (arguments.length < 2) {
        throw new TypeError('arguments error');
    }
    if (Reflect.has(this.handles, eventName)) {
        EventsList = this.handles[eventName].eventsList;
    } else {
        this.handles[eventName] = {
            eventsList: [callback],
            isOne: false,
        };
    }
    EventsList.push(callback);
}

PubSub.prototype.notify = function (eventName, ...rest) {
    if (this.handles[eventName]) {
        let EventsList = this.handles[eventName].eventsList, i = 0, isOne = this.handles[eventName].isOne;
        if (EventsList) {
            for (; i < EventsList.length; i++) {
                EventsList[i].apply(this, rest)
            }
        }
        if (isOne) {
            this.unsubscribe(eventName)
        }
    }
    return this;
}

const myPub = new PubSub();

myPub.subscribe('event', function (data) {
    console.log('触发');
    console.log(data)
})
document.getElementById('btn').onclick = function () {
    myPub.notify('event', 123);
} 
