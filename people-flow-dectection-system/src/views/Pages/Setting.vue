<template>
  <div>
    <base-header class="pb-6 pb-8 pt-5 pt-md-8 bg-gradient-success">
      <!-- Card stats -->
      <b-row>
        <b-col xl="3" md="6">
          <stats-card title="实时人数"
                      type="gradient-red"
                      sub-title="78"
                      icon="ni ni-air-baloon"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">2.98%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="进入监控区域人数"
                      type="gradient-orange"
                      sub-title="56"
                      icon="ni ni-bold-right"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">10.97%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="离开监控区域人数"
                      type="gradient-green"
                      sub-title="24"
                      icon="ni ni-bold-left"
                      class="mb-4">

            <template slot="footer">
              <span class="text-danger mr-2">5.72%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>

        </b-col>
        <b-col xl="3" md="6">
          <stats-card title="平均停留时间 (s)"
                      type="gradient-info"
                      sub-title="37.8"
                      icon="ni ni-time-alarm"
                      class="mb-4">

            <template slot="footer">
              <span class="text-success mr-2">24.8%</span>
              <span class="text-nowrap">相比于一个小时前</span>
            </template>
          </stats-card>
        </b-col>
      </b-row>
    </base-header>
    <!--   <div class="header pb-8 pt-5 pt-lg-8 d-flex align-items-center profile-header"
        style="min-height: 600px; background-image: url(img/theme/profile-cover.jpg); background-size: cover; background-position: center top;">
      <b-container fluid>
        <!- Mask ->
        <span class="mask bg-gradient-success opacity-8"></span>
        <!- Header container ->
        <b-container fluid class="d-flex align-items-center">
          <b-row >
            <b-col lg="7" md="10">
              <h1 class="display-2 text-white">Hello Jesse</h1>
              <p class="text-white mt-0 mb-5">This is your profile page. You can see the progress you've made with your
                work and manage your projects or assigned tasks</p>
              <a href="#!" class="btn btn-info">Edit profile</a>
            </b-col>
          </b-row>
        </b-container>
      </b-container>
    </div>

    <b-container fluid class="mt--6">
      <b-row>
        <b-col xl="4" class="order-xl-2 mb-5">
          <user-card></user-card>
        </b-col>
        <b-col xl="8" class="order-xl-1">
          <edit-profile-form></edit-profile-form>
        </b-col>
      </b-row>
    </b-container> -->
  </div>
</template>
<script>
import EditProfileForm from "./UserProfile/EditProfileForm.vue";
import UserCard from "./UserProfile/UserCard.vue";

export default {
  components: {
    EditProfileForm,
    UserCard,
  },
};
</script>
<style></style>
