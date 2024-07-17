<template>
    <div class="fireworks-container" ref="fireworksContainer">
        <h1 ref="text" class="hidden-text">ABCDERFSERGAGAEGG</h1>
    </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';
import { Fireworks } from 'fireworks-js'

export default {
    name: 'FireworksToText',
    mounted() {
        this.fireworksAnimation().then(() => {
            this.textAnimation();
        })
        console.log('anime')
    },

    methods: {
        fireworksAnimation() {
            return new Promise((resolve) => {
                const fireworksContainer = this.$refs.fireworksContainer;
                const fireworks = new Fireworks(fireworksContainer, {
                    autoresize: true,
                    opacity: 0.5,
                    acceleration: 1.05,
                    friction: 0.97,
                    gravity: 1.5,
                    particles: 50,
                    traceLength: 3,
                    traceSpeed: 10,
                    explosion: 5,
                    intensity: 30,
                    flickering: 50,
                    lineStyle: 'round',
                    hue: {
                        min: 0,
                        max: 360
                    },
                    delay: {
                        min: 30,
                        max: 60
                    },
                    rocketsPoint: {
                        min: 50,
                        max: 50
                    },
                    lineWidth: {
                        explosion: {
                            min: 1,
                            max: 3
                        },
                        trace: {
                            min: 1,
                            max: 2
                        }
                    },
                    brightness: {
                        min: 50,
                        max: 80
                    },
                    decay: {
                        min: 0.015,
                        max: 0.03
                    },
                    mouse: {
                        click: false,
                        move: false,
                        max: 1
                    }
                })
                console.log('firework')
                fireworks.start();
                // Giả lập hiệu ứng pháo hoa
                anime({
                    targets: fireworksContainer,
                    backgroundColor: ['#fff', '#42b983'],
                    easing: 'easeInOutSine',
                    duration: 2000,
                    complete: resolve
                });
            });
        },
        textAnimation() {
            const text = this.$refs.text;
            text.classList.remove('hidden-text');
            anime({
                targets: text,
                opacity: [0, 1],
                duration: 2000,
                easing: 'easeInOutQuad'
            });
        }
    }
}
</script>

<style scoped>
.fireworks-container {
    position: relative;
    width: 100%;
    height: 100vh;
    background-color: #000;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    z-index: 1;
}

h1 {
    font-size: 3em;
    color: #fff;
    opacity: 0;
}

.hidden-text {
    opacity: 0;
}
</style>