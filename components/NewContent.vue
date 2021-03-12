<template>
    <div class="card text-center">
        <div class="card-header">
            <span class="text-muted">Whats on mind ?</span>
        </div>
        <div class="card-body">
            <div class="row justify-content-around">
                <div>
                    <button class="btn btn-success"><i style="color:yellow" class="far fa-file-alt fa-lg"></i></button>
                    <br>
                    <small>Documents</small>
                </div>
                <div>
                    <button class="btn btn-success"><i style="color:yellow" class="fas fa-camera-retro fa-lg"></i></button>
                    <br>
                    <small>Photos</small>
                </div>
                <div>
                    <button class="btn btn-success"><i style="color:yellow" class="fas fa-video fa-lg"></i></button>
                    <br>
                    <small>Videos</small>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'NewContent'
}
</script>
