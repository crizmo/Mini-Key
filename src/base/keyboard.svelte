<script>
	import '../base/css/keyboard.css';

    function keyPressed(e) {
		if(e.key === e.key.toUpperCase()) {
			document.getElementById(e.key.toLowerCase()).style.backgroundColor = "black";
			document.getElementById(e.key.toLowerCase()).style.color = "white";
			setTimeout(function() {
				document.getElementById(e.key.toLowerCase()).style.backgroundColor = "";
				document.getElementById(e.key.toLowerCase()).style.color = "";
			}, 200);
		}
		else {
			document.getElementById(e.key).style.backgroundColor = "black";
			document.getElementById(e.key).style.color = "white";
			setTimeout(function() {
				document.getElementById(e.key).style.backgroundColor = "";
				document.getElementById(e.key).style.color = "";
			}, 200);
		}
    }
    document.addEventListener('keydown', keyPressed);

</script>

<main>
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
