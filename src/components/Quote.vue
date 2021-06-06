<template>
    <div class="col-sm-6 col-md-4 col-lg-3 mb-3">
        <div class="card shadow-sm">
            <div class="card-body quote">
                <slot></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default{

    }
</script>

<style >
    @import url('https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap');
    .card-body{
        /* font-family: 'Arizonia, cursive'; */
        font-family: 'Dancing Script', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }
    .quote{
        cursor: pointer;
    }
    .quote:hover{
        background-color: #ffe2e2;
    }
</style>