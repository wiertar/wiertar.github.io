<template>
    <div>
        <div class="modal__outside" :style="getCss" @click="doModal">
        
        </div>
        <div class="modal">
            <div class="modal__details" :style="getCss">
                <span class="modal__button modal__button--exit" @click="doModal">X</span>
                {{ pData }}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: [
        'pData'
    ],
    data: function() {
        return {
            display: true,
        }
    },
    methods: {
        doModal: function() {
            this.display = !this.display;
        }  
    },
    computed: {
        getCss: function() {
            return this.display ? "display: block" : "display: none";
        },
        display: function() {
            return this.display;
        }
    },
    mounted() {
        console.log('here!');
        setInterval(function() {
            if (this.display === false)
                this.display = true;
        }, 5000);
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
    width: 0;
    height: 0;
    &__details {
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
        width: 45%;
        height: 45%;
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

