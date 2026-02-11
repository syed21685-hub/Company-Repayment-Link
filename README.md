# Company-Repayment-Link
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Payment Link</title>
</head>
<body>
    <h2>Payment Details</h2>
    Amount: <input type="text" id="amount"><br>
    Name: <input type="text" id="name"><br>
    VPA: <input type="text" id="vpa"><br>

    <script>
        // Get URL params
        const urlParams = new URLSearchParams(window.location.search);
        document.getElementById('amount').value = urlParams.get('amntInput') || '';
        document.getElementById('name').value = urlParams.get('nameInput') || '';
        document.getElementById('vpa').value = urlParams.get('vpaInput') || '';
    </script>
</body>
</html>
