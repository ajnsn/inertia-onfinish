<template>
    <div>Hello World <inertia-link href="/" preserve-state>Reload</inertia-link></div>
</template>

<script>
export default {
    props: {
        triggerReload: Boolean,
    },
    watch: {
        triggerReload() {
            this.reload();
        },
    },
    methods: {
        reload() {
            this.$inertia.visit('/', {
                preserveState: true,
                onBefore: () => {
                    console.log('onBefore');
                },
                onFinish: () => {
                    console.log('onFinish');
                },
            });
        },
    },
};
</script>
