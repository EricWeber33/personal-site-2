<script lang="ts">
    export let repo:any;
</script>

<a href={repo.url}>
    <div class="p-4 bg-surface-700 my-2 hover:bg-surface-600 md:h-36 relative">
        <h3 class="text-2xl font-serif">
            {repo.name}
        </h3>
        <p>
            {#if repo.description}
                {repo.description}
            {:else}
                No description available.
            {/if}
        </p>
        <div class="flex flex-wrap md:absolute bottom-0 my-4">
            {#each repo.languages.nodes as language}
            <div class="flex flex-row">
                <div style="background: {language.color};" class="rounded-full h-2 w-2 my-auto mx-1"></div>
                <span> {language.name}&nbsp;&nbsp;</span>
            </div>
            {/each}
        </div>
    </div>
</a>
