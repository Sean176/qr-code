<!DOCTYPE html>
<html>
<head>
    <title>QR Code Generator</title>
    <!-- Mock-up code by Dr. F 12.26.22 -->
</head>
<body style="background-color:sandybrown;">
    <h2 style="color:black; text-align: center;">UI QR Code Basic Generator</h2>
    <center>
        <!-- The input field where the user can enter the text or URL to encode in the QR code -->
        <input type="text" id="qr-code-value" placeholder="Enter text or URL">

        <!-- The button that will trigger the QR code generation -->
        <button onclick="generateQRCode()">Generate QR Code</button>

        <!-- The img element where the QR code image will be displayed -->
        <img id="qr-code-image" alt="QR code">
    </center>

    <!-- Include the QRious library -->
    <!-- <script src="qrious.min.js"></script> -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrious/4.0.2/qrious.min.js"></script>
    
    <script>
        function generateQRCode() {
            // Get the value entered by the user
            const value = document.getElementById('qr-code-value').value;

            // Set the options for the QR code
            const options = {
                value: value, // The text or URL to encode in the QR code
                size: 400,    // The size of the QR code in pixels
                level: 'H'    // The error correction level of the QR code
            };

            // Create a new QR code object
            const qrCode = new QRious(options);

            // Get the QR code image as a data URL
            const qrCodeImage = qrCode.toDataURL();

            // Display the QR code image on the webpage
            document.getElementById('qr-code-image').src = qrCodeImage;
        }
    </script>
</body>
</html>
