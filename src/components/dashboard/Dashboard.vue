<template>
    <div>
        <v-container>
            <v-app-bar
                :elevation="0"
                style="
                    display: flex; 
                    align-items: center; 
                    justify-content: space-between;
                "
            >
                <template v-slot:prepend>
                    <a href="/" style="display: flex; align-items: start;">
                        <img style="width: 100%;" class="dashlogo" src="../../assets/logo.svg" alt="logo">
                    </a>                
                </template>
                <template v-slot:append>
                    <button class="button dashbtn" style="margin-top: 0px; color: #021c40;">
                        <a href="/" style="color: #021c40;">
                            Sign Out
                        </a>
                    </button>
                </template>
            </v-app-bar>
            <v-main style="padding-top: 40px !important;">
                <div class="dashboard-top">
                    <h2>$1,905,830.26<span>{{ " " }}(PND)</span></h2>
                    <p>William Dean MCcoy Jr<span>{{ " " }}Current account</span></p>
                </div>
                <div class="dashboard-table">
                    <v-table
                        fixed-header
                        height="75dvh"
                        class="dashboard-table-cover"
                    >
                        <thead>
                            <tr>
                                <th class="text-left">
                                    Date
                                </th>
                                <th class="text-left">
                                    Description
                                </th>
                                <th class="text-left">
                                    Type
                                </th>
                                <th class="text-left">
                                    Amount
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td class="text-left">08/23/2024</td>
                                <td class="text-left">Account Transfer from Lana Candis</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$1,905,830.26</td>
                            </tr>
                        </tbody>
                    </v-table>
                </div>
            </v-main>
        </v-container>
    </div>
</template>

<script>
export default {
    name: "DashboardComp",
    data() {
        return {
            datas: [
                {
                    date: "08/23/2024",
                    description: "Account Transfer from Lana Candis",
                    type: "Credit",
                    amount: "$1,905,830.26",
                },
            ],
        }
    },
}
</script>

<style lang="scss" scoped>
@import "../../scss/Dashboard.scss";

.v-container {
    padding: 0px !important;

    .v-toolbar__content {
        height: 100% !important;
        display: block !important;
        transition: inherit;
        width: 100%;
    }
}
</style>
