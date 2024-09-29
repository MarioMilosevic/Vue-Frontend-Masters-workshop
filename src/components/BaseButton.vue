<script>
export default {
    props: {
        text: String,
        icon:String
}
};
</script>

<template>
    <button>{{ icon }} - {{ text }}</button>
</template>
