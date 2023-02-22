<template>
<ul>
<li v-for="content in contents" :key="content.id">
<nuxt-link :to="`/${content.id}`">
{{ content.title }}
</nuxt-link>
</li>
</ul>
</template>

<script>
import axios from 'axios'
export default {
async asyncData() {
const { data } = await axios.get(
// your-service-id部分は自分のサービスidに置き換えてください
'https://inpact.microcms.io/api/v1/blog',
{
// your-api-key部分は自分のapi-keyに置き換えてください
headers: { 'X-MICROCMS-API-KEY': 'ka9LG7WqE5yvW619R2ss1oK7r0tfxRbsIjuf' }
}
)
return data
}
}
</script>
