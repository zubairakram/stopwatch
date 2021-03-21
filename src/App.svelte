<script>
    let isStarted = false;
    let hours = 0;
    let minutes = 0;
    let seconds = 0;
    let milliseconds = 0;
    let interval;


    function counter() {
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


    function start() {

        if (!interval) {
            isStarted = true;
            interval = setInterval(counter, 10);
        }

    }

    function stop() {
        if (interval) {
            isStarted = false;
            clearInterval(interval);
            interval = null;
        }
    }

    function reset() {
        stop();
        hours = 0;
        minutes = 0;
        seconds = 0;
        milliseconds = 0;

    }

    function format(n) {
        if (n < 10) {
            return `0${n}`;
        } else {
            return n;
        }
    }
</script>

<main>
    <div>{ format(hours) }h : { format(minutes) }m : { format(seconds) }s : { format(milliseconds) }</div>

    {#if isStarted}
        <button on:click={ stop }>STOP</button>
    {:else}
        <button on:click={ start }>START</button>
    {/if}
    <button on:click={ reset }>RESET</button>
</main>

<style></style>
