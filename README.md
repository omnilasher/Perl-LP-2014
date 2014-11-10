#------------TELEFONO.PL---------
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
