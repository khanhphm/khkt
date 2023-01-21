<template>

  <v-container>
    <div class="justify-center d-flex mb-8">
      <v-chip elevation="6" color="primary" class="pa-6 ">
        <h1>TRA CỨU THÔNG TIN</h1>
      </v-chip>
    </div>

    <v-row>
      <v-col>
        <v-card>
          <v-card-title>
            <h3>Danh Sách Học Sinh</h3> 
            <v-spacer></v-spacer>
            <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" placeholder="Tìm theo tên, ngày sinh, lớp, niên khoá, ID"
              hide-details></v-text-field>
          </v-card-title>
          <v-data-table multi-sort :loading="desserts == []" sort-by="id" items-per-page="7" fixed-header
            :headers="headers" :items="desserts" :search="search"></v-data-table>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data()
  {
    return {
      search: '',
      headers: [
        { text: "ID", value: "id" },
        { text: "Họ tên", value: "name" },
        { text: "Ngày sinh", value: "birth" },
        { text: "Lớp", value: "class" },
        { text: "Năm tốt nghiệp", value: "year" },
      ],
      desserts: [
        { name: "Jane Manning", birth: "24/03/2005", class: "A9", id: "24", year: "2026" },
        { name: "Isaiah Webb", birth: "09/04/2005", class: "A1", id: "12", year: "2026" },
        { name: "Elizabeth Bennett", birth: "02/12/2005", class: "A6", id: "136", year: "2023" },
        { name: "Dollie Drake", birth: "23/08/2005", class: "A10", id: "241", year: "2023" },
        { name: "Lucy Weaver", birth: "11/06/2005", class: "A8", id: "128", year: "2024" },
        { name: "Jeremy Steele", birth: "02/06/2005", class: "A5", id: "162", year: "2025" },
        { name: "Maggie Frazier", birth: "02/03/2005", class: "A10", id: "175", year: "2026" },
        { name: "Winnie Ballard", birth: "19/12/2005", class: "A5", id: "107", year: "2024" },
        { name: "Edwin Pratt", birth: "01/12/2005", class: "A4", id: "232", year: "2026" },
        { name: "Lillian Wright", birth: "04/11/2005", class: "A11", id: "103", year: "2023" },
        { name: "Marvin Crawford", birth: "11/05/2005", class: "A3", id: "32", year: "2023" },
        { name: "Mittie Padilla", birth: "06/03/2005", class: "A7", id: "186", year: "2026" },
        { name: "Willie Coleman", birth: "18/07/2005", class: "A9", id: "114", year: "2023" },
        { name: "Blake Cobb", birth: "24/05/2005", class: "A12", id: "154", year: "2023" },
        { name: "Ann Roy", birth: "08/02/2005", class: "A1", id: "222", year: "2023" },
        { name: "Nathan Harrington", birth: "29/04/2005", class: "A11", id: "104", year: "2023" },
        { name: "Andre Stone", birth: "18/06/2005", class: "A6", id: "243", year: "2023" },
        { name: "Clayton Higgins", birth: "14/10/2005", class: "A10", id: "66", year: "2023" },
        { name: "Richard Boyd", birth: "15/09/2005", class: "A1", id: "131", year: "2025" },
        { name: "Marguerite Wright", birth: "24/07/2005", class: "A11", id: "162", year: "2025" },
        { name: "Adam Burton", birth: "11/10/2005", class: "A4", id: "234", year: "2025" },
        { name: "Sue Coleman", birth: "16/08/2005", class: "A12", id: "86", year: "2026" },
        { name: "Phoebe Matthews", birth: "11/09/2005", class: "A10", id: "174", year: "2023" },
        { name: "Gertrude Yates", birth: "30/05/2005", class: "A8", id: "299", year: "2025" },
        { name: "Mable Diaz", birth: "05/04/2005", class: "A3", id: "275", year: "2025" },
        { name: "Johnny Freeman", birth: "13/04/2005", class: "A9", id: "271", year: "2024" },
        { name: "Carrie Day", birth: "07/11/2005", class: "A12", id: "237", year: "2024" },
        { name: "Daniel Jordan", birth: "16/05/2005", class: "A12", id: "224", year: "2023" },
        { name: "Helena Lamb", birth: "31/03/2005", class: "A5", id: "221", year: "2023" },
        { name: "Jackson McCormick", birth: "24/09/2005", class: "A1", id: "250", year: "2026" },
        { name: "Lucas Howell", birth: "24/11/2005", class: "A1", id: "297", year: "2025" },
        { name: "Dorothy Quinn", birth: "15/02/2005", class: "A3", id: "214", year: "2023" },
        { name: "Vincent Hale", birth: "03/11/2005", class: "A10", id: "224", year: "2025" },
        { name: "Lenora Peters", birth: "07/11/2005", class: "A7", id: "247", year: "2023" },
        { name: "Tillie Simmons", birth: "17/11/2005", class: "A9", id: "222", year: "2025" },
        { name: "Chad Ray", birth: "31/10/2005", class: "A7", id: "213", year: "2023" },
        { name: "James Nichols", birth: "26/08/2005", class: "A7", id: "282", year: "2023" },
        { name: "Lola Aguilar", birth: "09/03/2005", class: "A6", id: "268", year: "2023" },
        { name: "Edith Roberts", birth: "30/08/2005", class: "A8", id: "254", year: "2025" },
        { name: "Teresa Craig", birth: "03/08/2005", class: "A11", id: "253", year: "2026" },
        { name: "Polly Warren", birth: "03/04/2005", class: "A7", id: "224", year: "2026" },
        { name: "Landon Keller", birth: "23/07/2005", class: "A6", id: "214", year: "2023" },
        { name: "Miguel Cook", birth: "15/01/2005", class: "A9", id: "201", year: "2023" },
        { name: "Franklin Armstrong", birth: "26/11/2005", class: "A5", id: "281", year: "2026" },
        { name: "Myrtie Murphy", birth: "27/06/2005", class: "A4", id: "283", year: "2025" },
        { name: "Tony Carpenter", birth: "25/05/2005", class: "A6", id: "229", year: "2024" },
        { name: "Myrtle Rodgers", birth: "26/01/2005", class: "A7", id: "219", year: "2024" },
        { name: "Roy Brooks", birth: "19/08/2005", class: "A1", id: "202", year: "2025" },
        { name: "Ryan Tucker", birth: "28/12/2005", class: "A7", id: "257", year: "2024" },
        { name: "Gabriel Johnson", birth: "22/01/2005", class: "A10", id: "278", year: "2024" },
        { name: "Peter Ballard", birth: "19/03/2005", class: "A3", id: "214", year: "2025" },
        { name: "Francis Ramsey", birth: "15/02/2005", class: "A1", id: "230", year: "2024" },
        { name: "Winifred Walton", birth: "21/11/2005", class: "A7", id: "210", year: "2024" },
        { name: "Alberta Martinez", birth: "02/05/2005", class: "A5", id: "210", year: "2024" },
        { name: "Evan Cohen", birth: "12/05/2005", class: "A9", id: "294", year: "2024" },
        { name: "Lottie Daniels", birth: "02/04/2005", class: "A11", id: "229", year: "2024" },
        { name: "Joseph Munoz", birth: "16/05/2005", class: "A7", id: "254", year: "2024" },
        { name: "Alice Logan", birth: "27/07/2005", class: "A12", id: "282", year: "2025" },
        { name: "Della Kelly", birth: "05/09/2005", class: "A10", id: "285", year: "2025" },
        { name: "Lawrence Owen", birth: "10/06/2005", class: "A2", id: "214", year: "2024" },
        { name: "Miguel Ramos", birth: "17/04/2005", class: "A10", id: "215", year: "2025" },
        { name: "Beatrice Hayes", birth: "20/08/2005", class: "A8", id: "212", year: "2023" },
        { name: "Isabel Houston", birth: "23/11/2005", class: "A11", id: "258", year: "2023" },
        { name: "Johnny Flores", birth: "01/07/2005", class: "A8", id: "228", year: "2023" },
        { name: "Gary Moody", birth: "28/05/2005", class: "A4", id: "250", year: "2025" },
        { name: "Michael Foster", birth: "26/06/2005", class: "A1", id: "298", year: "2023" },
        { name: "Josie Farmer", birth: "07/09/2005", class: "A7", id: "245", year: "2024" },
        { name: "Mary McLaughlin", birth: "30/07/2005", class: "A7", id: "236", year: "2025" },
        { name: "Lloyd Abbott", birth: "22/05/2005", class: "A10", id: "274", year: "2024" },
        { name: "Vernon Garrett", birth: "18/10/2005", class: "A12", id: "240", year: "2024" },
        { name: "Lida Jimenez", birth: "16/10/2005", class: "A8", id: "293", year: "2023" },
        { name: "Jose Stevenson", birth: "21/08/2005", class: "A6", id: "219", year: "2025" },
        { name: "Jared Kennedy", birth: "16/04/2005", class: "A7", id: "233", year: "2025" },
        { name: "Alejandro Tucker", birth: "12/10/2005", class: "A10", id: "255", year: "2023" },
        { name: "Douglas Haynes", birth: "09/09/2005", class: "A6", id: "202", year: "2025" },
        { name: "Jeremy Jenkins", birth: "31/10/2005", class: "A11", id: "220", year: "2025" },
        { name: "Lena Hogan", birth: "08/11/2005", class: "A6", id: "263", year: "2025" },
        { name: "Polly Colon", birth: "27/05/2005", class: "A5", id: "265", year: "2025" },
        { name: "Agnes Bates", birth: "18/01/2005", class: "A7", id: "225", year: "2024" },
        { name: "Gertrude Rogers", birth: "19/12/2005", class: "A8", id: "243", year: "2025" },
        { name: "Bettie Phillips", birth: "07/04/2005", class: "A1", id: "256", year: "2023" },
        { name: "Emily Castro", birth: "03/04/2005", class: "A4", id: "258", year: "2024" },
        { name: "Harvey Griffin", birth: "08/08/2005", class: "A6", id: "226", year: "2024" },
        { name: "Cordelia Kim", birth: "28/06/2005", class: "A1", id: "227", year: "2026" },
        { name: "Ronald Bates", birth: "13/10/2005", class: "A6", id: "243", year: "2024" },
        { name: "Donald Sandoval", birth: "09/05/2005", class: "A10", id: "293", year: "2025" },
        { name: "Bess Porter", birth: "07/02/2005", class: "A1", id: "250", year: "2025" },
        { name: "Paul French", birth: "27/05/2005", class: "A8", id: "249", year: "2025" },
        { name: "Kevin Wells", birth: "19/05/2005", class: "A10", id: "239", year: "2026" },
        { name: "Clyde Dennis", birth: "29/07/2005", class: "A4", id: "293", year: "2024" },
        { name: "Nina Lane", birth: "07/07/2005", class: "A4", id: "214", year: "2024" },
        { name: "Francis Adkins", birth: "24/08/2005", class: "A8", id: "275", year: "2025" },
        { name: "Rachel Estrada", birth: "03/08/2005", class: "A11", id: "236", year: "2024" },
        { name: "Isaiah Thomas", birth: "11/02/2005", class: "A7", id: "232", year: "2025" },
        { name: "Matilda Herrera", birth: "04/11/2005", class: "A6", id: "278", year: "2026" },
        { name: "Joel Logan", birth: "11/06/2005", class: "A9", id: "273", year: "2024" },
        { name: "Joe Guerrero", birth: "09/03/2005", class: "A10", id: "240", year: "2025" },
        { name: "Jim Watson", birth: "15/10/2005", class: "A11", id: "275", year: "2026" },
        { name: "Lida Diaz", birth: "28/03/2005", class: "A6", id: "286", year: "2026" },
        { name: "Charles Logan", birth: "02/08/2005", class: "A7", id: "250", year: "2023" },
        { name: "Christina Chapman", birth: "15/02/2005", class: "A6", id: "224", year: "2026" },
        { name: "Ricardo Myers", birth: "22/05/2005", class: "A5", id: "257", year: "2026" },
        { name: "Duane Snyder", birth: "15/05/2005", class: "A1", id: "265", year: "2023" },
        { name: "Frances Collier", birth: "08/07/2005", class: "A9", id: "286", year: "2023" },
        { name: "Myrtie Bradley", birth: "19/06/2005", class: "A12", id: "263", year: "2023" },
        { name: "Catherine Griffin", birth: "10/08/2005", class: "A9", id: "288", year: "2024" },
        { name: "Nellie Underwood", birth: "04/05/2005", class: "A5", id: "299", year: "2024" },
        { name: "Genevieve Wilkins", birth: "19/07/2005", class: "A11", id: "266", year: "2024" },
        { name: "Daisy Hicks", birth: "20/09/2005", class: "A9", id: "213", year: "2025" },
        { name: "Rodney Webb", birth: "20/02/2005", class: "A1", id: "205", year: "2025" },
        { name: "Irene Bowers", birth: "02/02/2005", class: "A9", id: "238", year: "2024" },
        { name: "Chase Lawson", birth: "04/02/2005", class: "A4", id: "234", year: "2026" },
        { name: "Cecelia Lambert", birth: "07/07/2005", class: "A1", id: "295", year: "2024" },
        { name: "Maggie Clayton", birth: "13/06/2005", class: "A3", id: "202", year: "2025" },
        { name: "Linnie Wood", birth: "14/09/2005", class: "A4", id: "291", year: "2025" },
        { name: "Hulda Taylor", birth: "24/03/2005", class: "A3", id: "260", year: "2026" },
        { name: "Travis James", birth: "31/10/2005", class: "A7", id: "264", year: "2025" },
        { name: "Millie Osborne", birth: "14/04/2005", class: "A2", id: "299", year: "2024" },
        { name: "Phoebe Valdez", birth: "05/01/2005", class: "A10", id: "204", year: "2026" },
        { name: "Jordan Bishop", birth: "30/04/2005", class: "A12", id: "299", year: "2024" },
        { name: "Jay Ellis", birth: "26/03/2005", class: "A7", id: "257", year: "2026" },
        { name: "Raymond Roberson", birth: "28/05/2005", class: "A1", id: "202", year: "2024" },
        { name: "Blake Gray", birth: "24/02/2005", class: "A11", id: "217", year: "2024" },
        { name: "Jeffrey Figueroa", birth: "01/04/2005", class: "A10", id: "200", year: "2025" },
        { name: "Dale Gill", birth: "05/07/2005", class: "A10", id: "266", year: "2025" },
        { name: "Clifford Pratt", birth: "24/08/2005", class: "A10", id: "245", year: "2024" },
        { name: "Cody Chambers", birth: "29/12/2005", class: "A7", id: "206", year: "2024" },
        { name: "Florence Wheeler", birth: "16/12/2005", class: "A5", id: "243", year: "2024" },
        { name: "Cynthia Campbell", birth: "03/06/2005", class: "A2", id: "214", year: "2023" },
        { name: "Keith Jordan", birth: "13/03/2005", class: "A1", id: "278", year: "2023" },
        { name: "Connor Clark", birth: "01/06/2005", class: "A5", id: "256", year: "2026" },
        { name: "Randy Benson", birth: "09/05/2005", class: "A10", id: "249", year: "2023" },
        { name: "Adrian Castillo", birth: "22/05/2005", class: "A8", id: "251", year: "2026" },
      ]
    }
  },
}
</script>
