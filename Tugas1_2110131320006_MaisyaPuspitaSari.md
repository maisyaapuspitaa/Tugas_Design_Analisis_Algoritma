Nama : Maisya Puspita Sari
NIM : 2110131320006

____________
## Penjelasan Sederhana Tentang Time Complexity dan Big-O Notation

<p align = "right"><i> Asep Maulana Ismail <br> 3 Desember 2016 <br></i> <a href = "https://medium.com/bee-solution-partners/penjelasan-sederhana-tentang-time-complexity-dan-big-o-notation-4337ba275cfe" >On Medium</a></p>

    Every good programmer will use the most effective and efficient ways to solve their problem. And to do that, we must know how to minimize the complexity.

<p align = "justify"> Setiap programmer yang baik akan menggunakan cara yang paling efektif dan efisien dalam menyelesaikan suatu permasalahan. Dan untuk bisa melakukan hal tersebut, kita harus bisa meminimalisir kompleksitas dari algoritma yang kita gunakan.</p>

Kompleksitas suatu algoritma dibagi menjadi 2, yaitu Time Complexity dan Space Complexity.

<p align = "justify"> Time Complexity adalah seberapa lama waktu yang diperlukan untuk menjalankan suatu algoritma. Sedangkan Space Complexity adalah seberapa besar memori yang kita gunakan untuk menjalankan suatu algoritma. Dan disini kita hanya akan membahas tentang Time Complexity.</p>

    Algorithm is a process or set of rules to be followed in calculations or other problem-solving operations, especially by a computer.

<p align = "justify">  algoritma adalah serangkaian proses yang dilakukan secara berurutan untuk menyelesaikan sebuah permasalahan. Algoritma bisa bermacam-macam tergantung kepada siapa yang membuat algoritma tersebut. </p>

<p align = "justify"> Time Complexity Analysis adalah suatu cara sederhana untuk mengetahui berapa lama waktu yang dibutuhkan untuk menjalankan suatu algoritma dengan input tertentu (n). Biasanya lebih dikenal dengan sebutan Big-O Notation.</p>

Big O Notation digunakan untuk mengukur tingkat kompleksitas suatu algoritma.

**So, What’s Big-O Notation?**

    Big-O notation is a way of converting the overall steps of an algorithm into algebraic terms, then excluding lower order constants and coefficients that don’t have that big an impact on the overall complexity of the problem.

<p align = "justify"> Big-O Notation adalah cara untuk mengkonversi keseluruhan langkah-langkah suatu algoritma kedalam bentuk Aljabar, yaitu dengan menghiraukan konstanta yang lebih kecil dan koefisien yang tidak berdampak besar terhadap keseluruhan kompleksitas permasalahan yang diselesaikan oleh algoritma tersebut.</P>

    Regular       Big-O
    2             O(1)   --> It's just a constant number
    2n + 10       O(n)   --> n has the largest effect
    5n^2          O(n^2) --> n^2 has the largest effect

Sederhananya,  “*kita hanya akan melihat faktor yang memiliki dampak paling besar terhadap nilai yang dihasilkan oleh algoritma tersebut*”.

### O(1) — Constant Time
    O(1) — Constant Time: Given an input of size n, it only takes a single step for the algorithm to accomplish the task

<p align = "justify"> Constant Time artinya banyaknya input yang diberikan kepada sebuah algoritma, tidak akan mempengaruhi waktu proses (runtime) dari algoritma tersebut.</P>

    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
    function getFirst(input){
        return input[0]; // selalu melakukan 1 langkah
    }
    let firstEl = getFirst(myArray);

<p align = "justify"> Contoh diatas, terdapat sebuah fungsi untuk mengambil elemen pertama dari sebuah input array. Kita bisa melihat bahwa berapapun jumlah array yang diberikan kepada fungsi tersebut, dia akan selalu melakukan 1 hal, yaitu mengambil elemen pertama. Itu artinya <b> jumlah input yang diberikan tidak mempengaruhi waktu proses (runtime) dari algoritma tersebut.</b></P>

<p align = "center"><img src = "Constant Time.png"></p>

### O(log n) — Logarithmic Time
    O(log n) — Logarithmic time: given an input of size n, the number of steps it takes to accomplish the task are decreased by some factor with each step.

<p align = "justify"> Logarithmic Time artinya ketika kita memberikan input sebesar n terhadap sebuah fungsi, jumlah tahapan yang dilakukan oleh fungsi tersebut berkurang berdasarkan suatu faktor. Salah satu contohnya adalah algoritma Binary Search.</P>

<p align = "justify"> Binary Search adalah algoritma yang kita gunakan dalam mencari posisi nilai dari suatu array dengan cara ‘mengeliminasi’ setengah dari array input untuk mempercepat proses pencarian.</P>

    let sortedArray = [11, 24, 30, 43, 51, 61, 73, 86];
    function isExists(number, array){
        var midPoint = Math.floor( array.length /2 );
        if( array[midPoint] === num) return true;
        let isFirstHalf = false;
        if( array[midPoint] < num ) isFirstHalf = true;
    
        else if( array[midpoint] > num ) isFirstHalf = false;
        if (array.length == 1) return false;
        else { 
            // memanggil fungsi yang sama dengan mengeleminiasi setengah dari input array
            if (isFirstHalf) 
                return isExists(number, getFirstHalf(array));
            else 
                return isExists(number, getSecondHalf(array));
        }
    }
    isExists (24, sortedArray); // return true
    isExists (27, sortedArray); // return false

### O(n) — Linear Time
    O(n) — Linear Time: Given an input of size n, the number of of steps required is directly related (1 to 1)

Linear Time adalah ketika runtime dari fungsi kita berbanding lurus dengan jumlah input yang diberikan.

    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
    function getMax(input){
        var max = 0;
        for (var i=0; i<input.length; i++){
            if (max < input[i])
                max = input[i];
        }
        return max;
    }
    let maxNumber = getMax(myArray);

**Semakin banyak jumlah input yang diberikan, maka waktu proses/runtime dari fungsi tersebut akan semakin besar.**

<p align = "center"><img src = "Linier Time.png"></p>

### O(n²) — Quadratic Time
    O(n²) — Quadratic Time: Given an input of size n, the number of steps it takes to accomplish a task is square of n.

<p align = "justify"> Quadratic Time adalah ketika runtime dari fungsi kita adalah sebesar n^2, dimana n adalah jumlah input dari fungsi tersebut. Hal tersebut bisa terjadi karena kita menjalankan fungsi linear didalam fungsi linear (n*n).</P>

    let myArray = [1, 5, 0, 6, 1, 9, 9, 2];
    function sort(input){
        var sortedArray = [];
        for (var i=0; i<input.length; i++){ // O(n)
            let min = input[i];
            for (var j=i+1; i<input.length; i++){ // O(n)
                if (input[i] < input[j])
                    min = input[j];
            }
            sortedArray.push(min);
        }
        return sortedArray;
    }
    let sortedArray = sort(myArray);

<p align = "center"><img src = "Quadratic Time.png"></p>

### O(2^n) — Exponential Time
    O(2^n) — Exponential Time: Given an input of size n, the number of steps it takes to accomplish a task is a constant to the n power (pretty large number).

<p align = "justify"> Exponential Time biasanya digunakan dalam situasi dimana kita tidak terlalu tahu terhadap permasalahan yang dihadapi, sehingga mengharuskan kita mencoba setiap kombinasi dan permutasi dari semua kemungkinan.</P>

<p align = "center"><img src = "Exponential Time.png"></p>