<script>
    let hours = 0;
let minutes = 0;
let seconds = 0;
let milliseconds = 0;

let interval = setInterval(start, 10);

function start() {
    milliseconds += 1;
    if (milliseconds > 99) {
        milliseconds = 0;
        seconds +=1;
        if (seconds > 59) {
            seconds = 0;
            minutes +=1;
            if (minutes > 59) {
                minutes = 0;
                hours +=1;
            }
        }
    }
}


function stop() {
    clearInterval(interval);
}

function reset() {
    hours = 0;
    minutes = 0;
    seconds = 0;
    milliseconds = 0;

}
</script>

<main>
    <div><span>{ hours }</span>h</div>
    <div><span>{ minutes }</span>m</div>
    <div><span>{ seconds }</span>s</div>
    <div><span>{ milliseconds }</span></div>

    <button on:click={ start }>START</button>
    <button on:click={ stop }>STOP</button>
    <button on:click={ reset }>RESET</button>
</main>

<style></style>
