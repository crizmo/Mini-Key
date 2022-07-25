<script>
	import '../base/css/key.css';

	let letters = 0;
	let time = 60;
	let isPlaying = false;
	let interval;
	let words = 0;
	let wpm = 0;

	let towrite = "Hi i am kurizu how are you !";

    function keyPressed(e) {

        console.log(e.key);
		letters++;

		if(e.key === e.key.toUpperCase()) {
			console.log('upper');
			document.getElementById(e.key.toLowerCase()).style.backgroundColor = "black";
			document.getElementById(e.key.toLowerCase()).style.color = "white";
			setTimeout(function() {
				document.getElementById(e.key.toLowerCase()).style.backgroundColor = "";
				document.getElementById(e.key.toLowerCase()).style.color = "";
			}, 200);
		}
		else {
			console.log('lower');
			document.getElementById(e.key).style.backgroundColor = "black";
			document.getElementById(e.key).style.color = "white";
			setTimeout(function() {
				document.getElementById(e.key).style.backgroundColor = "";
				document.getElementById(e.key).style.color = "";
			}, 200);
		}
		
		if(e.key == "Enter") {
			check();
			clearInterval(interval);
			isPlaying = false;
		}
    }

	function startGame() {
		isPlaying = true;
		interval = setInterval(function() {
			time--;
			if(time === 0) {
				check();
				clearInterval(interval);
				isPlaying = false;
			}
		}, 1000);
	}
	

	function check() {
		let text = document.getElementById('text').value;
		let words = text.split(/\s+/).filter(function(e) { return e.length > 0; });
		console.log(words);
		let wpmx = words.length / time * 60;
		wpm = wpmx.toFixed(2);

		if(isPlaying) {
			let text = document.getElementById('text').value;
			console.log(text);
			if(text === towrite) {
				alert('You won with ' + letters + ' letters and ' + time + ' seconds' + ' and ' + wpm + ' wpm');
			}
			else {
				alert('You lost');
			}
		} else {
			alert('Game is not started');
		}
	}

	function resetGame() {
		time = 60;
		letters = 0;
		isPlaying = false;
		words = 0;
		clearInterval(interval);
	}

    document.addEventListener('keydown', keyPressed);

</script>

<main>
	<div id="towrite">
		<p><span id="towrite-value">{towrite}</span></p>
	</div>
	<div id="textarea">
		<textarea id="text" rows="5" cols="100"></textarea>
	</div>
	<div id="lpm">
		<p>LPM: <span id="wpm-value">{letters}</span> LPM</p>
	</div>
	<div id="time">
		<p>Time: <span id="time-value">{time}</span></p>
	</div>
	<div id="words">
		<p>WPM: <span id="words-value">{wpm}</span></p>
	</div>
	<div id="start">
		<button on:click="{startGame}">Start</button>
	</div>
	<div id="reset">
		<button on:click="{resetGame}">Reset</button>
	</div>
	<div id="check">
		<button on:click="{check}">Check</button>
	</div>
	<div id="keyboard">
		<div class="row">
			<div id="1" class="key key-1">1</div>
			<div id="2" class="key key-2">2</div>
			<div id="3" class="key key-3">3</div>
			<div id="4" class="key key-4">4</div>
			<div id="5" class="key key-5">5</div>
			<div id="6" class="key key-6">6</div>
			<div id="7" class="key key-7">7</div>
			<div id="8" class="key key-8">8</div>
			<div id="9" class="key key-9">9</div>
			<div id="0" class="key key-0">0</div>
		</div>
		<div class="row">
			<div id="Tab" class="key-tab">tab</div>
			<div id="q" class="key key-q">q</div>
			<div id="w" class="key key-w">w</div>
			<div id="e" class="key key-e">e</div>
			<div id="r" class="key key-r">r</div>
			<div id="t" class="key key-t">t</div>
			<div id="y" class="key key-y">y</div>
			<div id="u" class="key key-u">u</div>
			<div id="i" class="key key-i">i</div>
			<div id="o" class="key key-o">o</div>
			<div id="p" class="key key-p">p</div>
			<div id="Backspace" class="key-backspace">back</div>
		</div>
		<div class="row">
			<div id="CapsLock" class="key-caps">caps</div>
			<div id="a" class="key key-a">a</div>
			<div id="s" class="key key-s">s</div>
			<div id="d" class="key key-d">d</div>
			<div id="f" class="key key-f">f</div>
			<div id="g" class="key key-g">g</div>
			<div id="h" class="key key-h">h</div>
			<div id="j" class="key key-j">j</div>
			<div id="k" class="key key-k">k</div>
			<div id="l" class="key key-l">l</div>
			<div id="Enter" class="key-enter">enter</div>
		</div>
		<div class="row">
			<div id="z" class="key key-z">z</div>
			<div id="x" class="key key-x">x</div>
			<div id="c" class="key key-c">c</div>
			<div id="v" class="key key-v">v</div>
			<div id="b" class="key key-b">b</div>
			<div id="n" class="key key-n">n</div>
			<div id="m" class="key key-m">m</div>
		</div>
		<div class="row">
			<div id="Control" class="key-ctrl">ctrl</div>
			<div id="Alt" class="key-alt">alt</div>
			<div id=" " class="key-space">space</div>
			<div id="Shift" class="key-shift">shift</div>
		</div>
	</div>
</main>
