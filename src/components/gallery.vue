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
        var len = this.images.length;           //Length of the images array
        var counter = 0;                        //a counter to define how much space is used
        for(var i = 0; i<len;i++){              //calc a value for each img
            if(counter >=5){counter=0;}         //The grid has 5 columns, therefore the limit is 5
            var rand = Math.floor(Math.random()*5) + 1;
            counter += rand;
            while (counter>5){                  //if counter exceeds 5, make the rand value of i smaller
                rand--;
                counter--;
            }
            if(i==(len-1) ){                    //fill up the space by the last item
                while(counter<5){
                    counter++;
                    rand++;
                }
            }
            var result = "col-span-" + rand.toString(); //create the css class string

            grArray[i]={id:this.images[i].id,src:this.images[i].src,rs:result};
        }
        return grArray;
    }
    },
    
}
</script>

<style scoped>

</style>