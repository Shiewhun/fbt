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
                <!-- <div class="logo">
                    <img src="../../assets/logo.svg" alt="logo">
                </div> -->
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
                            <tr
                                v-for="data in datas"
                                :key="data.name"
                            >
                                <td class="text-left">{{ data.date }}</td>
                                <td class="text-left">{{ data.description }}</td>
                                <td class="text-left">{{ data.type }}</td>
                                <td class="text-left">{{ data.amount }}</td>
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
                // datas: [
                //     {
                //         date: "01/14/2024",
                //         description: "POS DEBIT WALMART 9203846 CA",
                //         type: "Debit",
                //         amount: "$37.19",
                //     },
                //     {
                //         date: "01/11/2024",
                //         description: "POS DEBIT TARGET 7461923 FL",
                //         type: "Debit",
                //         amount: "$15.00",
                //     },
                //     {
                //         date: "01/08/2024",
                //         description: " ONLINE TRANSFER 9182734 NY ",
                //         type: "Credit",
                //         amount: "$1,500.00",
                //     },
                //     {
                //         date: "01/05/2024",
                //         description: "POS DEBIT NETFLIX.COM 8623945 CA",
                //         type: "Debit",
                //         amount: "$15.99",
                //     },
                //     {
                //         date: "01/02/2024",
                //         description: "POS DEBIT STARBUCKS 5487216 IL",
                //         type: "Debit",
                //         amount: "$3.25",
                //     },
                //     {
                //         date: "12/30/2023",
                //         description: "POS DEBIT AMAZON.COM/BILL 800-692-7753",
                //         type: "Debit",
                //         amount: "$64.33",
                //     },
                //     {
                //         date: "12/27/2023",
                //         description: "POS DEBIT APPLE.COM/BILL 800-692-7753 CA",
                //         type: "Debit",
                //         amount: "$12.99",
                //     },
                //     {
                //         date: "12/24/2023",
                //         description: "ONLINE TRANSFER 0987654321 9207561 TX",
                //         type: "Credit",
                //         amount: "$500.00",
                //     },
                //     {
                //         date: "12/21/2023",
                //         description: "POS DEBIT UBER 9207561 1234597 OH",
                //         type: "Debit",
                //         amount: "$22.50",
                //     },
                //     {
                //         date: "12/18/2023",
                //         description: "POS DEBIT WALMART 6738957 TN",
                //         type: "Debit",
                //         amount: "$56.27",
                //     },
                //     {
                //         date: "12/15/2023",
                //         description: "POS DEBIT TARGET3847531 NY",
                //         type: "Debit",
                //         amount: "$35.00",
                //     },
                //     {
                //         date: "12/12/2023",
                //         description: "ONLINE TRANSFER 760219843 CA",
                //         type: "Credit",
                //         amount: "$750.00",
                //     },
                //     {
                //         date: "12/09/2023",
                //         description: "POS DEBIT NETFLIX.COM 853028190 CA",
                //         type: "Debit",
                //         amount: "$15.99",
                //     },
                //     {
                //         date: "12/06/2023",
                //         description: "POS DEBIT STARBUCKS 390275463 CA",
                //         type: "Debit",
                //         amount: "$5.25",
                //     },
                //     {
                //         date: "12/03/2023",
                //         description: "POS DEBIT AMAZON.COM 931847507 TN",
                //         type: "Debit",
                //         amount: "$82.47",
                //     },
                //     {
                //         date: "11/30/2023",
                //         description: "POS DEBIT APPLE.COM/BILL 866-712-7753 CA",
                //         type: "Debit",
                //         amount: "$15.99",
                //     },
                //     {
                //         date: "11/27/2023",
                //         description: "ONLINE TRANSFER 925463891 SAN DIEGO CS",
                //         type: "Credit",
                //         amount: "$1,000.00",
                //     },
                //     {
                //         date: "11/24/2023",
                //         description: "POS DEBIT UBER 482640382 TN",
                //         type: "Debit",
                //         amount: "$18.00",
                //     },
                //     {
                //         date: "11/21/2023",
                //         description: "POS DEBIT WALMART 213905613 TX",
                //         type: "Debit",
                //         amount: "$47.63",
                //     },
                //     {
                //         date: "11/18/2023",
                //         description: "POS DEBIT TARGET 482649382 TN",
                //         type: "Debit",
                //         amount: "$25.00",
                //     },
                //     {
                //         date: "11/15/2023",
                //         description: "ONLINE TRANSFER 0987654321, SAN DIEGO CA",
                //         type: "Credit",
                //         amount: "$300.00",
                //     },
                //     {
                //         date: "11/12/2023",
                //         description: "POS DEBIT NETFLIX.COM 760321473 CA",
                //         type: "Debit",
                //         amount: "$15.99",
                //     },
                //     {
                //         date: "11/09/2023",
                //         description: "POS DEBIT STARBUCKS 238407765 TX",
                //         type: "Debit",
                //         amount: "$3.50",
                //     },
                //     {
                //         date: "11/06/2023",
                //         description: "POS DEBIT AMAZON.COM 759231065 TN",
                //         type: "Debit",
                //         amount: "$49.99",
                //     },
                //     {
                //         date: "11/03/2023",
                //         description: "ONLINE TRANSFER 1234567890 CA",
                //         type: "Credit",
                //         amount: "$500.00",
                //     },
                //     {
                //         date: "11/01/2023",
                //         description: "POS DEBIT APPLE.COM/BILL 800-692-7753 CA",
                //         type: "Debit",
                //         amount: "$12.99",
                //     },
                // ],
                
                datas: [
                    { date: "11/14/2023", description: "POS DEBIT NETFLIX.COM 760321473 CA", type: "Debit", amount: "-$15.99" },
                    { date: "11/09/2023", description: "POS DEBIT STARBUCKS 238407765 TX", type: "Debit", amount: "-$3.50" },
                    { date: "11/06/2023", description: "POS DEBIT AMAZON.COM 759231065 TN", type: "Debit", amount: "-$49.99" },
                    { date: "11/03/2023", description: "ONLINE TRANSFER 1234567890 CA", type: "Credit", amount: "$500.00" },
                    { date: "11/01/2023", description: "POS DEBIT APPLE.COM/BILL 800-692-7753 CA", type: "Debit", amount: "-$12.99" },
                    { date: "10/30/2023", description: "POS DEBIT AMAZON.COM/BILL 800-692-7753", type: "Debit", amount: "-$64.33" },
                    { date: "10/30/2023", description: "POS DEBIT Kroger Grocery Store 6789012 TX", type: "Debit", amount: "-$55.60" },
                    { date: "10/27/2023", description: "POS DEBIT Whataburger 9012345 TX", type: "Debit", amount: "-$20.30" },
                    { date: "10/27/2023", description: "POS DEBIT APPLE.COM/BILL 800-692-7753 CA", type: "Debit", amount: "-$12.99" },
                    { date: "10/24/2023", description: "POS DEBIT McDonald's Restaurant 3456789 TX", type: "Debit", amount: "-$12.45" },
                    { date: "10/24/2023", description: "ONLINE TRANSFER 0987654321 9207561 TX", type: "Credit", amount: "$500.00" },
                    { date: "10/21/2023", description: "POS DEBIT Starbucks Coffee 6789012 TX", type: "Debit", amount: "-$8.75" },
                    { date: "10/21/2023", description: "POS DEBIT UBER 9207561 1234597 OH", type: "Debit", amount: "-$22.50" },
                    { date: "10/18/2023", description: "POS DEBIT Target Store 7890123 TX", type: "Debit", amount: "-$45.99" },
                    { date: "10/18/2023", description: "POS DEBIT WALMART 6738957 TN", type: "Debit", amount: "-$56.27" },
                    { date: "10/15/2023", description: "POS DEBIT Walmart Supercenter 2345678 TX", type: "Debit", amount: "-$60.35" },
                    { date: "10/15/2023", description: "POS DEBIT TARGET3847531 NY", type: "Debit", amount: "-$35.00" },
                    { date: "10/12/2023", description: "POS DEBIT H-E-B Grocery Store 5678901 TX", type: "Debit", amount: "-$75.20" },
                    { date: "10/12/2023", description: "ONLINE TRANSFER 760219843 CA", type: "Credit", amount: "$750.00" },
                    { date: "10/09/2023", description: "POS DEBIT Shell Gas Station 4567890 TX", type: "Debit", amount: "-$40.50" },
                    { date: "10/09/2023", description: "POS DEBIT NETFLIX.COM 853028190 CA", type: "Debit", amount: "-$15.99" },
                    { date: "10/06/2023", description: "POS DEBIT CVS Pharmacy 8901234 TX", type: "Debit", amount: "-$25.75" },
                    { date: "10/06/2023", description: "POS DEBIT STARBUCKS 390275463 CA", type: "Debit", amount: "-$5.25" },
                    { date: "10/03/2023", description: "POS DEBIT 7-Eleven 1234567 TX", type: "Debit", amount: "-$10.00" },
                    { date: "10/03/2023", description: "POS DEBIT AMAZON.COM 931847507 TN", type: "Debit", amount: "-$82.47" },
                ],
            }
        },
    }
</script>

<style lang="scss" scoped>
@import "../../scss/Dashboard.scss";

.v-container{
    padding: 0px !important;

    .v-toolbar__content{
        height: 100% !important;
        // align-items: center;
        display: block !important;
        // flex: 0 0 auto;
        // position: relative;
        transition: inherit;
        width: 100%;

    }
}
</style>
