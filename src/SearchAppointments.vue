<template>
  <div class="row search-appointments">
    <div class="col-sm-offset-3 col-sm-6">

      <div class="input-group">

        <input
          id="SearchApts"
          placeholder="Search"
          type="text"
          class="form-control"
          aria-label="Search Appointments"
          v-model="searchTerm"
        />

        <div class="input-group-btn">
          <button type="button" class="btn btn-primary dropdown-toggle"
            data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Sort by: <span class="caret"></span></button>

            <ul class="dropdown-menu dropdown-menu-right">

              <li>
                <a
                  href="#"
                  id="petName"
                  @click="requestKeyChange('petName')"
                >
                  Pet Name
                  <span
                    v-if="myKey==='petName'"
                    class="glyphicon glyphicon-ok"
                  >    
                  </span>
                </a>
              </li>

              <li>
                <a
                  href="#"
                  id="aptDate"
                  @click="requestKeyChange('aptDate')"
                >
                  Date
                  <span
                    v-if="myKey==='aptDate'"
                    class="glyphicon glyphicon-ok"
                  >    
                  </span>
                </a>
              </li>

              <li>
                <a
                  href="#"
                  id="ownerName"
                  @click="requestKeyChange('petOwner')"
                >
                  Owner
                  <span
                    v-if="myKey==='petOwner'"
                    class="glyphicon glyphicon-ok"
                  >    
                  </span>
                </a>
              </li>

              <li role="separator" class="divider"></li>

              <li>
                <a
                  href="#"
                  id="asc"
                  @click="requestDirChange('asc')"
                >
                  Asc
                  <span
                    v-if="myDir==='asc'"
                    class="glyphicon glyphicon-ok"
                  >    
                  </span>
                </a>
              </li>

              <li>
                <a
                  href="#"
                  id="desc"
                  @click="requestDirChange('desc')"
                >
                  Desc
                  <span
                    v-if="myDir==='desc'"
                    class="glyphicon glyphicon-ok"
                  >    
                  </span>
                </a>
              </li>
            </ul>
        </div><!-- input-group-btn --> 
      </div><!-- input-group --> 
    </div><!-- col-sm-offset-3 --> 
  </div><!-- search-appointments -->
</template>

<script>
export default {

  name: 'SearchAppointments',
  data() {
    return{
      searchTerm: ''
    }
  },
  watch: {
    searchTerm: function(){
      this.$emit('searchRecords', this.searchTerm)
    }
  },

  props: ['myKey', 'myDir'],

  methods: {
    requestKeyChange(value){
      this.$emit("keyChange", value);
    },
    requestDirChange(value){
      this.$emit("dirChange", value);
    }
  }

} // export

</script>