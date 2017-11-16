<template>
    <div>
        <div class="wrapper-tools">
            <div class="tool-ui" @click="switchGridLine">
                <span class="tool-ui-grid" :class=" { 'is-active': this.uiTypeGrid  } ">&#9783;</span>
                <span class="tool-ui-grid" :class=" { 'is-active': !this.uiTypeGrid  } ">&#9776;</span>
            </div>
            <div class="tool-ui" @click="switchSortOrder">
                <span class="tool-ui-grid" v-if=" this.sortAsc ">&#8613;</span>
                <span class="tool-ui-grid" v-else>&#8615;</span>
            </div>
            <div class="tool-filter">
                <input class="filter" type="text" v-model="filter" :placeholder="'Filter ' + list.length + ' contacts'">
            </div>
        </div>
        <div class="wrapper-contacts" :class=" { 'show-as-list': !this.uiTypeGrid  } ">
            <!-- SEE HUMAN TXT -->
        </div>
    </div>
</template>

<script>
    import contact from './contact'
    export default {
        name: 'contactList',
        // Chilren list
        components: {
            contact
        },
        // Value from parent
        props: ['list'],
        // Dynamic data, rerender each time a variable change
        computed: {
            sortedAndFilteredList(){
                //TODO
                return this.list
            }
        },
        // Function executed when this component is mounted (after all rendering)
        mounted(){
            //TODO
        },
        data(){
            return {
                sort: null,
                filter: null,
                uiTypeGrid: true,
                sortAsc: true
            }
        },
        methods: {

            switchSortOrder(){
                // SEE HUMAN TXT
            },

            sortContacts(list, order){
               
                return list;
            },
            filterContacts(list){

                return list;
                //TODO
            }
        }

        }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

    .wrapper-contacts {
        display: flex;
        flex-wrap: wrap;
        align-content: flex-start;
        justify-content: space-between;
    }
    
    .wrapper-contacts.show-as-list {
        flex-direction: column;
        align-items:  center;
        /* border: 1px solid red; */
    }

    .wrapper-tools {
        display: flex;
        flex-wrap: wrap;
        align-content: flex-start;
        margin: 0 0 11px;
        /* border: 1px solid red; */
    }

    .tool-filter {
        display: flex;
        flex-wrap: no-wrap;
        align-content: flex-end;
        justify-content: flex-end;
        /* border: 1px solid red; */
        flex: 1 0 auto;
        padding: 0 11px;
    }

    .filter {
        width: calc( 100% - 44px );
        max-width: 600px;
        height: 56px;
        /* margin: 0 0 0 11px; */
        border: 2px solid #eee;
        border-radius: 4px;
        font-size: 28px;
        padding: 0 22px;
        font-weight: 300;
        outline: none;
    }

    .tool-ui {
        flex: 0 0 120px;
        display: flex;
        flex-wrap: wrap;
        align-content: flex-end;
        padding: 0 11px;
        /* border: 1px solid red; */
        font-size: 28px;
        cursor: pointer;
    }

        .tool-ui-grid {
            width: 32px;
            height: 56px;
            /* border: 1px solid red; */
            line-height: 56px;
            text-align: center;
            opacity: 0.3;
        }

        .tool-ui-grid.is-active {
            opacity: 1;
        }

</style>
