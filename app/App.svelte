<page>
    <actionBar title="Svelte Native App" />
    <stackLayout>
        <label class="info" horizontalAlignment="center" verticalAlignment="center" textWrap="true">
            <formattedString>
                <span class="fas" text="&#xf135;" />
                <span text=" {message}" />
            </formattedString>
        </label>
        <label text="val: {val}" />
        <button text="Go to Other" on:tap="{go}" />
    </stackLayout>
</page>

<script>
    import { navigate, showModal } from 'svelte-native';
    import { onMount } from 'svelte';

    import Other from './Other.svelte';

    let val = 0;
    let message = "Blank Svelte Native App"

    async function go() {
        val = await showModal({page: Other, stretched: false });
        //navigate({page: Other})
    }

    onMount(async () => {
        //setTimeout(async () => { await go(); }, 500);
        await go();
    });
</script>

<style>
    .info .fas {
        color: #3A53FF;
    }

    .info {
        font-size: 20;
    }
</style>
