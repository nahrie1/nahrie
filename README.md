<? php
///////////////////////////////////////////
/////// DICIPTAKAN Syaefullah Nahri ////////
//////www.facebook.com/nahrie.17///////
/////https://github.com/nahrie1//////
/////////////////////////////////////////

termasuk  'tri_req.php' ;

$ tri = new tri ();
$ imei = "868880043302499" ;
echo  "Masukkan No Telepon:" ;
$ msisdn = trim ( fgets ( STDIN ));
$ otp = $ tri -> request_otp ( $ msisdn , $ imei );
echo  $ otp [ 1 ]. "\ r \ n" ;
echo  "Masukkan OTP:" ;
$ otp = trim ( fgets ( STDIN ));
$ login = $ tri -> login ( $ msisdn , $ otp );
$ login = json_decode ( $ login , true );
$ bearer = $ login [ 'access_token' ];
$ id = $ tri -> trans ( $ bearer );
$ id = json_decode ( $ id , true );
$ id = $ id [ 'data' ] [ 0 ] [ 'rewardTransactionId' ];
untuk ( $ id1 = 1500 ; $ id1 < 1600 ; $ id1 ++)
{
  $ gas = $ tri -> klaim ( $ bearer , $ id , $ id1 );
  gema  $ gas . "\ r \ n" ;
  tidur ( 2 );
}


?>
