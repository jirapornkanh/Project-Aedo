<template>
  <div> 
    <CRow>
      <CCol lg="12">
        <CCard>
          <CCardHeader>
            <h1>Profile</h1>
          </CCardHeader>
          <CCardBody>
            <CForm>

              <CRow>
                <CCol sm="2">   
              <img class="circle" public="circle.png" />  
                </CCol>
                <CCol style="margin-top:3%" sm="5">
                <h3>Name : {{name}} {{surname}}</h3>
                <p>User ID : 5931501010</p>

              </CCol>
              </CRow><br>

              <CRow>
                <CCol sm="4">
                  <CInput
                    v-model ="name"
                    label="Name" 
                  />
                </CCol>

              <CCol sm="4 ">
                <CInput
                 v-model ="surname"
                label="Surname"
                value=""
               />
              </CCol>

              <CCol sm="2">
               <CSelect 
                v-model="selectgender"
                label="Gender"
                :options="gender"
              />
              </CCol>
               </CRow>

               <CRow>
                 <CCol sm="4">
                <CInput 
                v-model="date"
                label="Birthday"
                type="date"
              />
              </CCol>

              <CCol sm="2 ">
                <CInput
                v-model="age"
                label="Age"
                value=""
               />
              </CCol>

                <CCol sm="4">
               <CInput
               v-model="phone"
                  label="Phone"
                  prepend="+66"

                />
              </CCol>
            </CRow>

              <CRow>
                <CCol sm="8">
                <CSelect
                  v-model="selectcountry"
                  label="Country"
                  :options="country"
                />
              </CCol>
              </CRow>

              <CRow>
                <CCol sm="4">
                <CInput
                v-model="zipcode"
                label="Zip Code"
                />
                </CCol>
                
                <CCol sm="4">
                <CSelect
                v-model="selectprovince"
                  label="Province / State"
                  :options="province"
                />
              </CCol>
              </CRow>

              <CRow>
               <CCol sm="4">
                <CSelect
                v-model="selectdistrict"
                  label="District"
                  :options="district"
                /> 
                </CCol>
                
                <CCol sm="4">
                <CSelect
                 v-model="selectsubDistrict"
                  label="Sub-District"
                  :options="subDistrict"
                />
              </CCol>
              </CRow>
              
              <CRow>
                <CCol sm="8">
                  <CInput
                   v-model="address"
                    label="Address"
                  />
                </CCol>
              </CRow>

              <CRow>
                <CCol sm="8">
                  <CSelect
                  v-model="selectoccupation"
                  label="Occupation"
                  :options="occupation"
                  />
                 </CCol>
              </CRow>

              <CRow>
                <CCol sm="4">
                  <CInput
                  v-model="university"
                    label="University"
                  />
                </CCol>

                <CCol sm="4 ">
                  <CInput
                  v-model="school"
                  label="Faculty/School"
                  />
                </CCol>
              </CRow>

              <CRow>
                <CCol sm="8">
                  <CInput
                  v-model="major"
                    label="Major"
                  />
                </CCol>
              </CRow>
            </CForm>

          <CRow>
      <CCol col="2">
        <CButton block color="facebook">
          Facebook
        </CButton>
      </CCol>
    </CRow>
    <br>
    <CRow>
      <CCol col="2">
        <CButton block variant="outline" color="danger">
        Google
        </CButton>
          
      </CCol>
    </CRow>
          </CCardBody>
          
          <p align=right>
          <CCardFooter>
            <CButton v-on:click="update" type="update" size="4" color="success"> Update</CButton>
            <CButton type="cancel" class="btn btn-secondary">Cencel</CButton>
            
          </CCardFooter> </p>
        </CCard>
      </CCol>
    </CRow>
  </div>
</template>

<script>
export default {
  name: 'Demo',
  data () {
    return {
      selected: [], 
      show: true,
      horizontal: { label:'col-3', input:'col-9' },
      gender: ['Male', 'Female', 'Others'],
      country: ['Thailand','China','Myanmar','Korea'],
      province: ['Lampang','Chiang Rai','Bangkok'],
      district: ['Maeung'],
      subDistrict: ['Maeung'],
      occupation:['Student','Teacher','Others'],

      selectOptions: [
        'Option 1', 'Option 2', 'Option 3',
        { 
          value: ['some value', 'another value'], 
          label: 'Selected option'
        }
      ],
      selectedOption: ['some value', 'another value'],

      
      name: '',
      surname: '',
      selectgender:'',
      date:'',
      age:'',
      phone:'',
      selectcountry:'',
      zipcode:'',
      selectprovince:'',
      selectdistrict:'',
      selectsubDistrict:'',
      address:'',
      selectoccupation:'',
      university:'',
      school:'',
      major:''


    }
  },
  methods: {
     validator (val) {
      return val ? val.length >= 4 : false
    },
     update: function (event) {
       var body =  {};
       
       body.name = btoa(this.name)
       body.surname = btoa(this.surname)
       body.selectgender = btoa(this.selectgender)
       body.date = btoa(this.date)
       body.age = btoa(this.age)
       body.phone = btoa(this.phone)
       body.selectcountry = btoa(this.selectcountry)
       body.zipcode = btoa(this.zipcode)
       body.selectprovince = btoa(this.selectprovince)
       body.selectdistrict = btoa(this.selectdistrict)
       body.selectsubDistrict = btoa(this.selectsubDistrict)
       body.address = btoa(this.address)
       body.selectoccupation= btoa(this.selectoccupation)
       body.university = btoa(this.university)
       body.school = btoa(this.faculty)
       body.major = btoa(this.major)

       console.log(body)

       }

     }
  }
</script>


<style scoped>
.circle {
  height: 100px;
  width: 100px;
  border-radius: 50%;
  display: inline-block;
  border-style: solid;
  border-width: medium;
}
.center{
   text-align: center
}
</style>