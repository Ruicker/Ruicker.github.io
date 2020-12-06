<!DOCTYPE html>
<html>

<head>
	<title>综柜辅助工具</title>
</head>
<style type="text/css">
	table {
		table-layout: fixed;
		width: 50%;
	}

	input {
		width: 90%;
	}
</style>

<body>
	<h1>库存现金工具</h1>
	输入库存现金：<input type="text" name="" id="balance" style="width:40%" tabindex="1qz"
		oninput="value=value.replace(/^\.|[^\d\.]|(?<=\..*?)\./g,'').replace(/(\.[0-9]{2}).+/g,'$1')">
	<button onclick="start()">开始 </button>
	<br />
	<h2></h2>
	<table border="1">
		<tr>
			<th>面值</th>
			<th>数量</th>
			<th>金额</th>
			<th>数量比例</th>
			<th>锁定数量</th>
		</tr>
		<tr>
			<td>100元</td>
			<td><input type="text" name="number" id="n100" tabindex="2" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a100').value=value*100"></td>
			<td><input type="text" name="amount" readonly id="a100"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="20"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>50元</td>
			<td><input type="text" name="number" id="n50" tabindex="4" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a50').value=value*50"></td>
			<td><input type="text" name="amount" readonly id="a50"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="4"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>20元</td>
			<td><input type="text" name="number" id="n20" tabindex="5" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a20').value=value*20"></td>
			<td><input type="text" name="amount" readonly id="a20"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="4"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>10元</td>
			<td><input type="text" name="number" id="n10" tabindex="6" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a10').value=value*10"></td>
			<td><input type="text" name="amount" readonly id="a10"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="4"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>5元</td>
			<td><input type="text" name="number" id="n5" tabindex="7" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a5').value=value*5"></td>
			<td><input type="text" name="amount" readonly id="a5"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="4"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>1元</td>
			<td><input type="text" name="number" id="n1" tabindex="8" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a1').value=value*1"></td>
			<td><input type="text" name="amount" readonly id="a1"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="10"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>0.5元</td>
			<td><input type="text" name="number" id="n0.5" tabindex="9" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a0.5').value=value*5/10"></td>
			<td><input type="text" name="amount" readonly id="a0.5"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="2"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>0.1元</td>
			<td><input type="text" name="number" id="n0.1" tabindex="10" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a0.1').value=value*1/10"></td>
			<td><input type="text" name="amount" readonly id="a0.1"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="1"></td>
			<td><input type="checkbox" name="lock"></td>
		</tr>
		<tr>
			<td>0.01元</td>
			<td><input type="text" name="number" id="n0.01" tabindex="11" oninput="value=value.replace(/[^\d]/g,'')"
					onchange="document.getElementById('a0.01').value=value*1/100"></td>
			<td><input type="text" name="amount" readonly id="a0.01"></input></td>
			<td><input type="text" name="qz" oninput="value=value.replace(/[^\d]|(?<=\d{2})./g,'')"
					onblur="value==''?value=('0'):1" value="0"></td>
			<td><input type="checkbox" name="lock" checked></td>
		</tr>
	</table>
	<script type="text/javascript">
		var money = [100, 50, 20, 10, 5, 1, 0.5, 0.1, 0.01];
		money.forEach(function (item, index, array) { array[index] = item * 100; });
		var mqz = new Array(9), number = new Array(9), amount = new Array(9), qz = new Array(9), lock = new Array(9);
		function start() {
			var numberT = new Array(9), amountT = new Array(9), qzT = new Array(9), lockT = new Array(9);
			balance = parseFloat(document.getElementById("balance").value);
			balance = balance ? balance * 100 : 0;
			numberT = document.getElementsByName("number");
			amountT = document.getElementsByName("amount");
			qzT = document.getElementsByName("qz");
			lockT = document.getElementsByName('lock');
			customMoney = 0;

			for (let i = 0; i < 9; i++) {
				lock[i] = lockT[i].checked;
				number[i] = lock[i] ? parseInt(numberT[i].value) : 0;
				number[i] ? NaN : number[i] = 0;
				amount[i] = lock[i] ? parseFloat(amountT[i].value) : 0;
				// amount[i] = amount[i] ? amount[i] * 100 : 0;
				qz[i] = parseInt(qzT[i].value);
				qz[i] ? NaN : qz[i] = 0;
				if (!lock[i]) {
					mqz[i] = qz[i] * money[i];
				} else {
					mqz[i] = 0;
					customMoney += number[i] * money[i];
				}
				// console.log(mqz[i], number[i], amount[i], qz[i]);
			}

			//带比例分配数量(扣除10%以内数量用于随机分配)
			var t = (balance-customMoney) / eval(mqz.join('+'));
			for (let i = 0; i < 9; i++) {
				!lock[i] ? number[i] = Math.floor(t * qz[i] * (1 - Math.random() * 0.1)) : NaN;
				amount[i] = number[i] * money[i];
			}
			balance = balance - eval(amount.join('+'));
			// console.log(balance / 100);

			//随机分配(效率低，输入值不宜过高)
			while (balance > 100) {
				i = Math.floor(Math.random() * 9);
				if (!lock[i] && balance > money[i]) {
					number[i] += 1;
					amount[i] = number[i] * money[i];
					balance -= money[i];
				}
			}
			// console.log(balance / 100,number);

			// 最终清零
			for (let i = 0; i < 9; i++) {
				t = Math.floor(balance / money[i]);
				number[i] += t;
				amount[i] = number[i] * money[i];
				balance -= t * money[i];
			}



			for (let i = 0; i < 9; i++) {
				numberT[i].value = number[i];
				amount[i] /= 100;
				amountT[i].value = amount[i];
			}
		}
	</script>

</body>

</html>
