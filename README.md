# filesendwithcurl
$tmpfile = $_FILES['image']['tmp_name'];
$filename = basename($_FILES['image']['name']);

$data = array(
    'uploaded_file' => '@'.$tmpfile.';filename='.$filename,
);

$ch = curl_init();   
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
// set your other cURL options here (url, etc.)

curl_exec($ch);
