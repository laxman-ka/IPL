# IPL
info about ipl 
<?php
$cricketMatchesTxt = file_get_contents('http://cricapi.com/api/matches?apikey=kNcljKmZkwdlL5pQh44Sn9sdKaK2&type=Twenty20');//e with your API key
echo "<pre>";
	$lsit =  json_decode($cricketMatchesTxt, true);

foreach ($lsit['matches'] as $k => $v ) {
    if ($v['type'] != 'Twenty20' || substr($v['unique_id'], 0, 4) != 1136) {
        continue;
    } else {
        $ipl[] = $v;
    }
    
}

print_r($ipl);

?>
