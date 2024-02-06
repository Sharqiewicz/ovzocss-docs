<script lang='ts'>
    export let svg: string;
    export let title: string;
    export let description: string;
</script>

<div class='px-5 mx-5 my-3 py-3 flex justify-center align-center flex-col text-align-justify'>
    <img src={svg} alt={title} />
    <h3 class='font-h3'>{title}</h3>
    <p>{description}</p>
</div>
