#----------------EDAD.PL-----------------
#! /user/bin/perl

open (ARGV,'dataset.txt')|| die "$!\n";
while(<ARGV>){
	if($_ =~ /[E-Te-t]+ (\d{2})(\s)?[Aa]/){
		$edad = $1;
		print "Edad: ".$edad." años\n";
	}else{
		print " \n";

	}
	
}

#---------------PESO.PL------------------
#! /user/bin/perl

open (ARGV,'dataset.txt')|| die "$!\n";
while(<ARGV>){
	if($_ =~ /[P-Qp-q]eso.*([0-9]{3})+[a-sA-S]*(\slibras)/i){		
		$peso = $1;
		print "Peso: ".$peso."libras\n";
	}elsif($_ =~ /[P-Qp-q]eso ([0-9]{2,3})+[g-sG-S]*(\s[g-sG-S])*/i){
		$peso = $1;
		print "Peso: ".$peso."kg\n";
	}elsif($_ =~ /[A-Za-z]proximadamente ([0-9]{2,3})/i){
		$peso = $1;
		print "Peso: ".$peso."kg\n";
	}elsif($_ =~ /alrededor de (\d{2,3})/i){
		$peso = $1;
		print "Peso: ".$peso."kg\n";
	}else{
		print " \n";

	}
}
#----------------TELEFONO.PL-------------
#! /user/bin/perl

open (ARGV,'dataset.txt')|| die "$!\n";
while(<ARGV>){

	if($_ !~ /[Mm]atricula.*((199[0-9]|20[0-9]+)[0-9]+)/ && $_ =~ /[A-Ua-u].*(\d{10})/){
		$telef = $1;
		print "Telefono: ".$telef."\n";
	}elsif($_ !~ /[Mm]atricula.*((199[0-9]|20[0-9]+)[0-9]+)/ && $_ =~ /[A-Ua-u].* (\+593\s)(\d{8})/){
		$telef = $2;
		print "Telefono: 09".$telef."\n";
	}elsif($_ !~ /\s?([0-9]{9}\-?[0-9]).*().*/ && $_ =~ /(fono es) (\d{6,12})\,?/ ){
		$telef = $2;
		print "Telefono: ".$telef."\n";
	}else{
		print " \n";

	}
	
}
