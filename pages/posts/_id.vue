<template>
 <div class="a"> 
     <article>
     <h1>{{post.title}}</h1>
     <p>{{post.conetent}}</p>
     </article>
     <aside>
         <h3>Hello Boss</h3>
         <ul>
             <li v-for="releted in relatedPost ">
                <nuxt-link :to="{name:'posts-id',params:{id:releted.id}}">{{releted.title}}</nuxt-link>
             </li>
         </ul>
     </aside>
     </div>
</template>
<script>
 export default{
    data(){
     return{
         id:this.$route.params.id ,   //route concept
     posts:[
         {
             id:'a',
             title:'What is a?',
             conetent:'a is a alfabet'
         },
         {id:'b',
         title:'What is b?',
         conetent:'b is a alfabet'
     },
      { id:'c',
        title:'What is c?',
        conetent:'c is a alfabet'}]
    }},

    computed:{
     post(){
         return this.posts.find(post=>post.id===this.id)
     },
      relatedPost(){
      return this.posts.filter(post =>post.id !==this.id)
    }
    }
   

   
 }
</script>
<style>
.a{
    
    color:blueviolet;
}
</style>