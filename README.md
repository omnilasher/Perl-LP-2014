use Encode;
use strict;
use warnings;
use feature ':5.12';

binmode STDOUT, ":utf8";
use utf8;

open(FILE,"<:utf8", "file.txt");
my $archivo = IO::File->new("file.txt","r");
binmode($archivo,':utf8');
while(my $row=<$archivo>){
	print $row;
}
close FILE;


open (FILE,'<:encoding(UTF-8)',"file.txt");
while(my $row = <FILE>){
	print $row;
}
