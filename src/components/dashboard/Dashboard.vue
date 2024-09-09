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
                <div class="dashboard-top" style="display: flex; align-items: center; justify-content: space-between;">
                    <div>
                        <h2>$1,905,830.26<span>{{ " " }}(PND)</span></h2>
                        <p>William Dean McCoy Jr<span>{{ " " }}Current account</span></p>
                    </div>
                    <v-btn
                        disabled
                        class="transfer-btn"
                        style="
                            background-color: #e0e0e0; 
                            color: #757575; 
                            cursor: not-allowed; 
                            margin-left: 20px;
                        "
                    >
                        Transfer Funds
                    </v-btn>
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
                            <tr>
                                <td class="text-left">01/14/2024</td>
                                <td class="text-left">POS DEBIT WALMART 9203846 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$37.19</td>
                            </tr>
                            <tr>
                                <td class="text-left">01/11/2024</td>
                                <td class="text-left">POS DEBIT TARGET 7461923 FL</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$15.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">01/08/2024</td>
                                <td class="text-left">ONLINE TRANSFER 9182734 NY</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$1,500.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">01/05/2024</td>
                                <td class="text-left">POS DEBIT NETFLIX.COM 8623945 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$15.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">01/02/2024</td>
                                <td class="text-left">POS DEBIT STARBUCKS 5487216 IL</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$3.25</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/30/2023</td>
                                <td class="text-left">POS DEBIT AMAZON.COM/BILL 800-692-7753</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$64.33</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/27/2023</td>
                                <td class="text-left">POS DEBIT APPLE.COM/BILL 800-692-7753 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$12.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/24/2023</td>
                                <td class="text-left">ONLINE TRANSFER 0987654321 9207561 TX</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$500.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/21/2023</td>
                                <td class="text-left">POS DEBIT UBER 9207561 1234597 OH</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$22.50</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/18/2023</td>
                                <td class="text-left">POS DEBIT WALMART 6738957 TN</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$56.27</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/15/2023</td>
                                <td class="text-left">POS DEBIT TARGET3847531 NY</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$35.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/12/2023</td>
                                <td class="text-left">ONLINE TRANSFER 760219843 CA</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$750.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/09/2023</td>
                                <td class="text-left">POS DEBIT NETFLIX.COM 853028190 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$15.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/06/2023</td>
                                <td class="text-left">POS DEBIT STARBUCKS 390275463 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$5.25</td>
                            </tr>
                            <tr>
                                <td class="text-left">12/03/2023</td>
                                <td class="text-left">POS DEBIT AMAZON.COM 931847507 TN</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$82.47</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/30/2023</td>
                                <td class="text-left">POS DEBIT APPLE.COM/BILL 866-712-7753 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$15.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/27/2023</td>
                                <td class="text-left">ONLINE TRANSFER 925463891 SAN DIEGO CS</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$1,000.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/24/2023</td>
                                <td class="text-left">POS DEBIT UBER 482640382 TN</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$18.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/21/2023</td>
                                <td class="text-left">POS DEBIT WALMART 213905613 TX</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$47.63</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/18/2023</td>
                                <td class="text-left">POS DEBIT TARGET 482649382 TN</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$25.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/15/2023</td>
                                <td class="text-left">ONLINE TRANSFER 0987654321, SAN DIEGO CA</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$300.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/12/2023</td>
                                <td class="text-left">POS DEBIT NETFLIX.COM 760321473 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$15.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/09/2023</td>
                                <td class="text-left">POS DEBIT STARBUCKS 238407765 TX</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$3.50</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/06/2023</td>
                                <td class="text-left">POS DEBIT AMAZON.COM 759231065 TN</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$49.99</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/03/2023</td>
                                <td class="text-left">ONLINE TRANSFER 1234567890 CA</td>
                                <td class="text-left">Credit</td>
                                <td class="text-left">$500.00</td>
                            </tr>
                            <tr>
                                <td class="text-left">11/01/2023</td>
                                <td class="text-left">POS DEBIT APPLE.COM/BILL 800-692-7753 CA</td>
                                <td class="text-left">Debit</td>
                                <td class="text-left">$12.99</td>
                            </tr>
                        </tbody>
                    </v-table>
                </div>
            </v-main>
        </v-container>
    </div>
</template>
