
$smsApi = new SmsApi("toplusms.digicell.com.tr","username","password");

$request = new SendSingleSms();
$request->title = "Title";
$request->content = "Single sms gönderim testi";
$request->number = 905006662211;
$request->encoding = 0;
$request->sender = "Gönderen Başlığı";

//Ticari gönderimlerde true değeri girilmelidir.
//$request->commercial = true;

//Mesajların AHS sorgusuna sokulması istenmiyorsa true değeri girilmelidir.
//$request->skipAhsQuery = true;

//İleri tarihli gönderim için
//$request->sendingDate = "2021-01-10 13:00";

//Rapor push olarak alınmak isteniyorsa ilgili url girilir
//$request->pushUrl = "https://webhook.site/8d7ed0f7"

$response = $smsApi->sendSingleSms($request);

if($response->err == null){
echo "MessageId: ".$response->pkgID."\n";
}else{
echo "Status: ".$response->err->status."\n";
echo "Code: ".$response->err->code."\n";
echo "Message: ".$response->err->message."\n";
}					