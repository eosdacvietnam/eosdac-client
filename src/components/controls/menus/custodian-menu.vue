<template>
  <div>
    <q-collapsible
      group="main-menu-sub"
      v-if="getIsCustodian"
      class="animate-fade"
    >
      <template slot="header">
        <q-item-side :icon="$configFile.icon.cust_tools" color="text2" />
        <q-item-main :label="$t('menu.custodian_tools')" class="text-text1" />
      </template>
      <div class="bg-bg1">
        <q-item class="q-pl-lg animate-fade" link to="/custodian/create-msigs">
          <q-item-main
            :label="$t('menu.create_msigs')"
            class="text-text1 text-weight-light"
          />
        </q-item>
        <q-item class="q-pl-lg animate-fade" link to="/custodian/review-msigs">
          <q-item-main
            :label="$t('menu.vote_msigs')"
            class="text-text1 text-weight-light"
          />
        </q-item>
        <!--
        <q-item
          class="q-pl-lg animate-fade"
          link
          to="/custodian/review-worker-proposals"
        >
          <q-item-main
            :label="$t('menu.vote_worker_proposals')"
            class="text-text1 text-weight-light"
          />
        </q-item>
        -->

        <q-item class="q-pl-lg animate-fade" link to="/custodian/my-payments">
          <q-item-main
            :label="$t('menu.my_payments')"
            class="text-text1 text-weight-light"
          />
        </q-item>
        <q-item
          class="q-pl-lg animate-fade"
          link
          to="/custodian/dac-financials"
        >
          <q-item-main
            :label="$t('menu.dac_financials')"
            class="text-text1 text-weight-light"
          />
        </q-item>
      </div>
    </q-collapsible>

    <q-collapsible v-else group="main-menu-sub" class="animate-fade">
      <template slot="header">
        <q-item-side :icon="$configFile.icon.dactoken" color="text2" />
        <q-item-main
          :label="
            $t('menu.dac_activity', { dacname: $configFile.get('dacname') })
          "
          class="text-text1"
        />
      </template>
      <div class="bg-bg1">
        <q-item class="q-pl-lg animate-fade" link to="/custodian/review-msigs">
          <q-item-main
            :label="$t('menu.view_msigs')"
            class="text-text1 text-weight-light"
          />
        </q-item>

        <!--
        <q-item
          class="q-pl-lg animate-fade"
          link
          to="/custodian/review-worker-proposals"
        >
          <q-item-main
            :label="$t('menu.view_worker_proposals')"
            class="text-text1 text-weight-light"
          />
        </q-item>
        -->
        <q-item
          class="q-pl-lg animate-fade"
          link
          to="/custodian/dac-financials"
        >
          <q-item-main
            :label="$t('menu.dac_financials')"
            class="text-text1 text-weight-light"
          />
        </q-item>
      </div>
    </q-collapsible>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  name: "custodianMenu",
  data() {
    return {};
  },
  computed: {
    ...mapGetters({
      getAccountName: "user/getAccountName",
      getIsCustodian: "user/getIsCustodian"
    })
  }
};
</script>

<style></style>
