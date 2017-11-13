<template>
    <div class="card" :class=" { 'show-as-block': !this.uiTypeGrid  } ">
        <span class="card__delete" @click="deleteContact">&#215;</span>
        <div class="card__person">
            <div class="card__avatar">
                <img :src="contact.pic" />
            </div>
            <div class="card__gns">
                <div class="card-line card__gender">
                    <label class="card-label" :for=" 'gender-' + contact.id "> Gender:</label>
                    <select class="card-select" :id=" 'gender-' + contact.id " v-model="contact.gender">
                        <option value="Male">M</option>
                        <option value="Female">Mme</option>
                    </select>
                </div>
                <div class="card-line card__firstname">
                    <label class="card-label" :for=" 'firstname-' + contact.id "> First name:</label>
                    <input class="card-input" v-model="contact.first_name" :id=" 'firstname-' + contact.id " type="text" />
                </div>
                <div class="card-line card__lastname">
                    <label class="card-label" :for=" 'lastname-' + contact.id "> Last name:</label>
                    <input class="card-input" v-model="contact.last_name" :id=" 'lastname-' + contact.id " type="text" />
                </div>
            </div>
        </div>
        <div class="card__infos">
            <div class="card-line">
                <label class="card-label" :for=" 'job-' + contact.id "> Job:</label>
                <input class="card-input" :id=" 'job-' + contact.id " v-model="contact.job_title" type="text" />
            </div>
            <div class="card-line">
                <label class="card-label" :for=" 'email-' + contact.id "> Email:</label>
                <input class="card-input" :id=" 'email-' + contact.id " v-model="contact.email" type="text" />
            </div>
        </div>
    <!-- <div> TODO PHONEs </div> -->
    </div>
</template>

<script>
export default {
  name: "contact",
  props: ["contact","uiTypeGrid"],
  watch: {
    contact: {
      handler: function(val, oldVal) {
        console.log("change ", val);
      },
      deep: true
    }
  },
  methods: {
    deleteContact() {
      console.log("delete ", this.contact.id);
      //TODO
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .card {
        position: relative;
        border-radius: 8px;
        background-color: lighten(#666, 55%);
        margin: 6px;
        padding: 16px 22px;
        color: #666;
        width: auto;
        cursor: pointer;
        transition: all ease-out 0.2s;

        &:hover {
            background-color: lighten(#666, 50%);
            box-shadow: 0 34px 36px -12px rgba(#666, 0.4);
            z-index: 10;

            .card__delete {
                opacity: 0.2;

                &:hover {
                    opacity: 1;
                    font-size: 20px;
                }

            }

        }

        &.show-as-block {
            width: 50%;
            display: flex;
            flex-wrap: wrap;
            flex-direction: row;
            align-content: flex-start;
            align-items: stretch;
            justify-content: flex-start;
            
            .card__person {
                flex: 1 1 auto;
            }
            
            .card__infos {
                flex: 2 1 auto;
            }

        }

    }
    
    .card-line {
        display: flex;
        transition: all ease-out 0.2s;
        // margin: 2px 0;

        // &:hover {
        //     border-radius: 4px;
        //     background: white;
        // }

    }

    .card__infos {
        // border: 1px solid red;
    } 

    .card__person {
        display: flex;
        margin-bottom: 22px;
        align-content: flex-start;
        justify-content: flex-start;
        // border: 1px solid red;
    }

        .card__avatar {
            display: flex;
            flex-direction: column;
            justify-content: center;
            flex: 0 0 66px;
            width: 56px;
            // border: 1px solid red;
            // height: 52px;
            overflow: hidden;

            img {
                // flex: 0 0 52px;
                width: 52px;
                height: 52 px;
                padding: 0;
                margin: 0;
                border: 1px solid rgba(#666,0.5);
                background-color: white;
                border-radius: 52px;
            }

        }

        .card__gns {
            display: flex;
            flex-wrap: no-wrap;
            flex-direction: column;
            align-content: flex-start;
            justify-content: flex-start;
            flex: 1 0 auto;
            // padding-left: 11px;
            text-align: left;
            // border: 1px solid red;
        }

            .card__gender {
                // align-content: flex-start;
                // border: 1px solid red;
            }

            .card__firstname {
                // border: 1px solid red;
            }

            .card__lastname {
                // border: 1px solid red;
            }

    .card-label {
        flex: 0 0 auto;
        width: 70px;
        line-height: 24px;
        font-size: 12px;
        padding: 0 3px 0 0;
        text-align: right;
        opacity: 0.5;
    }

    .card-select {
        height: 22px;
        outline: none;
        background: none;
        font-size: 12px;
        color: #666;
        border: none;
        -webkit-appearance: none;
    }

    .card-input {
        flex: 1 1 auto;
        height: 21px;
        font-size: 12px;
        line-height: 20px;
        color: #666;
        border: none;
        border-bottom: 1px solid transparent;
        background: none;
        outline: none;
        -webkit-appearance: none;

        &:focus {
            border-bottom: 1px dashed #666;
        }

    }

    .card__delete {
        position: absolute;
        top: 6px;
        right: 6px;
        width: 22px;
        height: 22px;
        line-height: 22px;
        font-size: 16px;
        font-weight: bold;
        opacity: 0;
        transition: all ease-out 0.3s;
    }


</style>
