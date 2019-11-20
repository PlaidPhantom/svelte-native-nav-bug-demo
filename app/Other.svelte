<page>
    <actionBar title="Svelte Native App" />
    <stackLayout>
        <label class="info" horizontalAlignment="center" verticalAlignment="center" textWrap="true">
            <formattedString>
                <span class="fas" text="&#xf135;" />
                <span text=" The other page!" />
            </formattedString>
        </label>
        <button text="Go Back" on:tap="{back}" />
    </stackLayout>
</page>

<script>
    import { closeModal } from 'svelte-native';

    function back() {
        closeModal('other');
    }
</script>

<style>
    .info .fas {
        color: #3A53FF;
    }

    .info {
        font-size: 20;
    }
</style>
