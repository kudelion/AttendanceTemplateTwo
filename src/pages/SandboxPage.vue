<template>
    <div class="row">
        <div class="col-sm-4 bg-primary text-white">
            <ol class="list-group">
                <li>
                    <button v-for="toggle in statusItem" :key="toggle.id" v-on:click="InputItem = toggle.item">
                        {{toggle.status}}
                    </button>
                </li>
            </ol>
        </div>
        <div class="col-sm-4 bg-dark text-white">
            {{InputItem}}
        </div>
    </div>
</template>
 <script>
    export default{
        data() {
            return{

                url:'./assets/logo.png',
                isShow1: true,
                isShow2: true,

                InputItem: ' ',
                statusItem: [
                    {status:'Punch-In', item: 'PRESENT'},
                    {status:'Punch-Out', item: 'ABSENT'}
                ],
            }         
        }
    };
</script>
