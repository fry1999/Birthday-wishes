<template>
    <div class="birthday-message">
        <!-- <img src="@/assets/moon.jpg" alt="Moon" class="moon-image"> -->
        <h1 ref="text" class="hidden-text">CHÚC MỪNG SINH NHẬT CHỊ LAN</h1>
    </div>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';
export default {
    name: 'BirthdayMessage',

    mounted() {
        this.textAnimation()
    },

    methods: {
        textAnimation() {
            const text = this.$refs.text;
            text.classList.remove('hidden-text');
            anime({
                targets: text,
                opacity: [0, 1],
                duration: 20000,
                easing: 'easeInOutQuad',
                // translateX: 1,
                // rotate: '1turn',
                // backgroundColor: '#FFF',
            });

            // anime({
            //     targets: text,
            //     translateX: {
            //         value: '*=2.5', // 100px * 2.5 = '250px'
            //         duration: 1000
            //     },
            //     width: {
            //         value: '-=20px', // 28 - 20 = '8px'
            //         duration: 1800,
            //         easing: 'easeInOutSine'
            //     },
            //     rotate: {
            //         value: '+=2turn', // 0 + 2 = '2turn'
            //         duration: 1800,
            //         easing: 'easeInOutSine'
            //     },
            //     direction: 'alternate'
            // });


        }
    }

}

</script>

<style scoped>
.birthday-message {
    text-align: center;
    margin-top: 20%;
}

h1 {
    font-size: 3em;
    color: #42b983
}

.moon-image {
    width: 100px;
    height: 100px;
    margin-bottom: 20px;
}
</style>