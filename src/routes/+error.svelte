<script>
    import { page } from "$app/stores";
    import "$lib/styles/global.css";
    import Loading from "$lib/components/Loading.svelte";
</script>

<div class="error-info">
    <Loading />
    <h1>Oops.. something went wrong, please check again later!</h1>
    <p>{$page.status}: {$page.error?.message}</p>
</div>

<style>
    .error-info {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
    }

    h1 {
        text-align: center;
        color: rgba(17, 191, 174, 1);
    }

    p {
        text-align: center;
        color: rgba(27, 60, 89, 1);
    }
</style>
