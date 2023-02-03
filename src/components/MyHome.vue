<template>
<div>
    <h3 v-if="user">
        {{user.exampleInputName}}
        {{user.exampleInputEmail}}
        {{user.exampleInputPassword}}
        {{user.phoneNumber}}
        {{user.foryou}}
    </h3>
    <h3 v-if="!user">
        Начальная страница, авторизируйтесь.  
    </h3>
</div>
</template>

<script>

export default {
    name: 'MyHome',
    props:['user']
}
</script>