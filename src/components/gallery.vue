<template>
    <div class="grid grid-cols-5 gap-4 pt-10 px-6 max-w-screen-2xl">
        <div v-for="img in gridArray()" :key="img.id" class="flex max-h-40 lg:max-h-96" :class="img.rs">
            <img :src="img.src" :key="img.id" alt="" class="object-cover rounded-3xl">
        </div>
    </div>
</template>

<script>
export default {
    name: "Gallery",
    props: ['images'],
    methods: {gridArray:function(){
        var grArray = [];
        var len = this.images.length;
        var counter = 0;
        for(var i = 0; i<len;i++){
            if(counter >=5){counter=0;}
            var rand = Math.floor(Math.random()*5) + 1;
            counter += rand;
            while (counter>5){
                rand--;
                counter--;
                console.log("rand üü: " + rand + "counter = " + counter);
            }
            console.log("counter is: " + counter + "rand is: " + rand);
            console.log("i=" + i);
            if(i==(len-1) ){
                while(counter<5){
                    counter++;
                    rand++;
                }
            }
            var result = "col-span-" + rand.toString();

            grArray[i]={id:this.images[i].id,src:this.images[i].src,rs:result};
        }
        console.log(grArray);
        return grArray;
    }
    },
    
}
</script>

<style scoped>

</style>