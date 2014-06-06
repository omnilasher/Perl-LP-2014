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
