<template>
    <div>
        <div class="modal__outside" :style="getCss" @click="toggleModalFunction">
        
        </div>
        <div class="modal">
            <div class="modal__details" :style="getCss">
                <span class="modal__button modal__button--exit" @click="toggleModalFunction">X</span>
                <div class="modal__header">
                    <span>Name: </span>{{ pData.Name }}
                </div>
                <div class="modal__content">
                    <span>About: </span>{{ pData.About }}
                </div>
                <div class="modal__content">
                    <span>Technologies: </span>{{ pData.Technologies }}
                </div>
                <div lcass="modal__footer"></div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: [
        'pData',
        'display',
        'toggleModalFunction'
    ],
    data: function() {
        return {
            data: null
        }
    },
    methods: {
        // doModal: function() {
        //     this.display = !this.display;
        // }  
    },
    computed: {
        getCss: function() {
            return this.display ? "display: block" : "display: none";
        },
        // display: function() {
        //     return this.display;
        // }
    },
    mounted() {
    }
}
</script>
<style lang="scss" scoped>
@keyframes expand-width {
    0% {
        min-width: 0;
        width: 0;
    }
    100% {
        min-width: 15rem;
        width: 45%;
    }
}

@keyframes expand-height {
    0% {
        min-height: 0;
        height: 0;
    }
    100% {
        min-height: 15rem;
        height: 45%;
    }
}

.expand-width {
    display: inline-block;
    animation: expand-width;
    animation-delay: 3s;
    animation-duration: .3s;
    backface-visibility: none;
}

.expand-height {
    display: inline-block;
    animation: expand-height;
    animation-delay: .6s;
    animation-duration: .3s;
    backface-visibility: none;
}

.modal__outside {
    position: fixed;
    top: 0%;
    left: 0%;
    background-color: rgba(0, 0, 0, 0.4);
    height: 100%;
    width: 100%;
    z-index: 100;
}

.modal {
    &__details {
        text-align: left;
        justify-content: space-between;
        position: fixed;
        z-index: 200;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background: white;
        box-shadow: 1px 1px 6px rgba(0, 0, 0, 0.4);
        padding: 1rem;
        font-size: 2rem;
        min-width: 12rem;
        min-height: 12rem;
        width: 75%;
        height: auto;
        font-size: 1rem;
    }
    &__header, &__content, &__footer {
        width: 100%;
        margin: 1rem 0;
        color: dimgrey;
        span {
            color: black;
        }
    }
    &__button {
        display: flex;
        flex-direction: column;
        justify-content: center;
        overflow: hidden;
        box-shadow: 1px 1px 6px rgba(0, 0, 0, 0.4);
        &--exit {
            display: flex;
            justify-content: center;
            position: relative;
            left: 100%;
            top: 0%;
            color: red;
            border: 3px solid red;
            text-align: center;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            background-color: white;
            cursor: pointer;
            transform: translate(-25%, -75%);
            backface-visibility: none;
        }
    }
}
</style>

