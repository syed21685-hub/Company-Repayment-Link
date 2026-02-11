# Company-Repayment-Link
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Payment Gateway</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f2f2f2;
    text-align:center;
    padding:40px;
}
.box{
    background:white;
    padding:25px;
    border-radius:10px;
    max-width:400px;
    margin:auto;
    box-shadow:0 0 10px rgba(0,0,0,0.1);
}
input{
    width:100%;
    padding:10px;
    margin:10px 0;
    border:1px solid #ccc;
    border-radius:5px;
}
button{
    background:#28a745;
    color:white;
    padding:12px;
    border:none;
    width:100%;
    border-radius:5px;
    font-size:16px;
    cursor:pointer;
}
button:hover{
    background:#218838;
}
</style>
</head>

<body>

<div class="box">
    <h2>Secure Payment</h2>

    <input type="text" id="name" placeholder="Name">
    <input type="text" id="amount" placeholder="Amount">
    <input type="text" id="upi" placeholder="UPI ID">

    <button onclick="payNow()">Pay Now</button>
</div>

<script>

// Get URL parameters
const params = new URLSearchParams(window.location.search);

document.getElementById("name").value = params.get("nameInput") || "";
document.getElementById("amount").value = params.get("amntInput") || "";
document.getElementById("upi").value = params.get("vpaInput") || "";

// Generate UPI Payment Link
function payNow(){
    let name = document.getElementById("name").value;
    let amount = document.getElementById("amount").value;
    let upi = document.getElementById("upi").value;

    if(!name || !amount || !upi){
        alert("Please fill all fields");
        return;
    }

    let upiLink = `upi://pay?pa=${upi}&pn=${name}&am=${amount}&cu=INR`;

    window.location.href = upiLink;
}

</script>

</body>
</html>
