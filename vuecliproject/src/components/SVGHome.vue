<template>
    <div id="app">
        <div class="container">
            <input v-model="floor" placeholder="3">
            <p>Message is: {{ floor }}</p>
            <input v-model="window" placeholder="3">
            <p>Message is: {{ window }}</p>
            <button v-on:click="amountGet">GO!</button>
            <svg viewBox="0 0 1000 1000" xmlns="http://www.w3.org/2000/svg">
            </svg>


        </div>
    </div>
</template>

<script>

    export default {
        data() {
            return {
                floor: 3,
                window: 4,
                floorAmount: 3,
                windowAmount: 4,
                widthfloor: 1000,
                heightfloor: 110,
                widthWindow: 90,
                heightWindow: 90,
                svg: "",
                floorParameters: function (floory) {
                    let height = this.heightfloor;
                    let width = this.widthfloor;
                    let floorBlock = document.createElementNS("http://www.w3.org/2000/svg", 'rect'); //Create a path in SVG's namespace
                    floorBlock.setAttribute("y", floory);
                    floorBlock.setAttribute("width", width);
                    floorBlock.setAttribute("height", height);
                    floorBlock.setAttribute("fill", "yellow");
                    return floorBlock;
                },
                windowParameters: function (windowx, windowy) {
                    let height = this.heightWindow;
                    let margin = this.margin();
                    this.widthWindow = (this.widthfloor - (margin * this.windowAmount) - margin) / this.windowAmount;
                    let width = this.widthWindow;
                    let windowBlock = document.createElementNS("http://www.w3.org/2000/svg", 'rect'); //Create a path in SVG's namespace
                    windowBlock.setAttribute("x", windowx);
                    windowBlock.setAttribute("y", windowy);
                    windowBlock.setAttribute("width", width);
                    windowBlock.setAttribute("height", height);
                    windowBlock.setAttribute("fill", "green");
                    return windowBlock;
                }
            }
        },
        components: {},
        methods: {
            amountValidating: function (x) {
                if (isNaN(x) || x < 1 || x > 10) {
                    x = 1;
                }
                return x;
            },
            build: function () {
                let floory = this.margin();
                for (let i = 0; i < this.floorAmount; i++) {
                    let newfloor = this.floorParameters(floory);
                    this.svg.appendChild(newfloor);
                    var windowx = this.margin();
                    for (let j = 0; j < this.windowAmount; j++) {
                        let windowy = floory + this.margin();
                        let newWindow = this.windowParameters(windowx, windowy);
                        this.svg.appendChild(newWindow);
                        windowx += this.widthWindow + this.margin();
                    }
                    floory += this.heightfloor;
                }
            },
            amountGet: function () {
                this.floorAmount = this.amountValidating(this.floor);
                this.windowAmount = this.amountValidating(this.window);
                this.defineSVG();
                this.clearSVG();
                this.build();
            },
            margin: function () {
                return ((this.heightfloor - this.heightWindow) / 2);
            },

            defineSVG() {
                this.svg = document.getElementsByTagName('svg')[0]; //Get svg element
            },

            clearSVG() {
                this.svg.innerHTML = "";
            }
        }
    }
</script>

<style>

</style>