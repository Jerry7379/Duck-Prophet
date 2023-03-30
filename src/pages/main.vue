<template>
    <div>
        <h1>APP</h1>

        <router-link :to="{ name: 'login' }"><button>login</button></router-link>

        <router-link :to="{ name: 'home' }" style="margin-left: 10px"><button>去瞧瞧css</button></router-link>
    </div>
</template>