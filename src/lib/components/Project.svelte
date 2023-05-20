<script lang="ts">
    import { Avatar } from "@skeletonlabs/skeleton";

    export let imgSrc:string;
    export let link:string
</script>

<div class="w-full xl:w-1/2 p-2 md:p-4">
    <div class="bg-primary-500 w-full md:h-[700px] relative">
        <div class="bg-gradient-to-t from-primary-500 from-50% to-secondary-500 to-50% pt-8 px-8 w-full">
            <div class="rounded-full border-8 border-primary-500 w-52 md:w-[19rem]  mx-auto">
                <Avatar src={imgSrc} class="border-8 border-secondary-500 w-48 md:w-72"></Avatar>
            </div>
        </div>
        <div class="bg-primary-500 pb-4 px-8">
            <h3 class="text-3xl text-center my-4 font-serif">
                <slot name="name"></slot>
                <hr class="border-none h-2 bg-secondary-500">
            </h3>
            <p class="text-lg text-center">
                <slot name="description"></slot>
            </p>
        </div>
        <div class="p-4 w-full flex justify-center xl:absolute xl:bottom-0">
            <a href={link} class="">
                <button class="btn-lg variant-ghost-secondary hover:bg-secondary-500/50">See more!</button>
            </a>
        </div>
    </div>
</div>