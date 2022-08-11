<template>
    <div>
        <Master>
            <div class="col-md-8 mx-auto mt-5">
                <div class="jumbotron">
                <h2 class="display-4">Hello, Guy!</h2>
                <p class="lead">
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla commodi nostrum dolores tempore exercitationem, error quaerat voluptas!
                </p>
                <hr class="my-4">
                <p>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis inventore dolorum iure facilis.
                </p>
                <a href="" class="btn btn-primary btn-lg">Learn more</a>
            </div>
            </div>
        </Master>
    </div>
</template>

<script>
import Master from '../Layout/Master.vue'
export default {
    name: 'Home-Page',
    components: {Master}
}
</script>