<template>

    <tr>
        <td>{{ item.name }}</td>
        <td>{{ item.age }}</td>
        <td>
            <button @iten="item.id">Удалить</button>
        </td>
    </tr>


</template>

<script>
export default {
    props: ['item'],


}
</script>