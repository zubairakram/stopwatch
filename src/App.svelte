<script>
    class StopWatch {
            this.hours = 0;
            this.minutes = 0;
            this.seconds = 0;
            this.milliseconds = 0;
            this.interval;

        counter() {
            this.milliseconds += 1;

            if (this.milliseconds > 99) {
                this.milliseconds = 0;
                this.seconds +=1;

                if (this.seconds > 59) {
                    this.seconds = 0;
                    this.minutes +=1;

                    if (this.minutes > 59) {
                        this.minutes = 0;
                        this.hours +=1;
                    }
                }
            }
        }

        start() {
            if (!this.interval) {
                this.interval = setInterval(()this.counter, 10);
                console.log(this.interval);
                console.log(this.counter);
            }
        }

        stop() {
            if (this.interval) {
                clearInterval(this.interval);
                this.interval = null;
            }
        }

        reset() {
            this.hours = 0;
            this.minutes = 0;
            this.seconds = 0;
            this.milliseconds = 0;
        }
    }

    let stopwatch = new StopWatch();

</script>

<main>
    <div><span>{ stopwatch.hours }</span>h</div>
    <div><span>{ stopwatch.minutes }</span>m</div>
    <div><span>{ stopwatch.seconds }</span>s</div>
    <div><span>{ stopwatch.milliseconds }</span></div>

    <button on:click={ stopwatch.start }>START</button>
    <button on:click={ stopwatch.stop }>STOP</button>
    <button on:click={ stopwatch.reset }>RESET</button>
</main>

<style></style>
