<template>
    <div>
        <b-col cols="12" class="mt-2 mb-2" id="header-metrics" style="font-size:13px"> Resource Uptime
            <b-nav-item-dropdown class="ddown2" no-caret>
            <template slot="button-content"> &#x22EE; </template>
                <b-dropdown-item> <v-icon name="edit"/> Edit </b-dropdown-item>
                <b-dropdown-item> <v-icon name="trash"/> Delete </b-dropdown-item>
            </b-nav-item-dropdown> 
        </b-col>
        <div class="margin-top">
            <h3>
                4d 22h 16m
            </h3>
        </div>
    </div>
</template>

<style scoped>
.margin-top {
  margin-top: 2.5em
}
</style>