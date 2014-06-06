sub validarCedula{
	$total=0;
	$mult=0;
	@cedula = @_;
	for($i=0;$i<10;$i++){
		$numero = chop(@cedula);
		push(@id,$numero);
	}
	@id = reverse(@id);	
	
	if( @id == 10 ){
		for($i = 0 ; $i < @id-1 ; $i++ ){
			$mult = 0;
			if( $i%2 != 0 ){#el indice es par
				$total = $total + $id[$i];
			}else{#el indice es impar
				$mult = $id[$i]*2;
				if($mult > 9){
					$total = $total + ($mult - 9);
				}else{
					$total = $total + $mult;
				}
			 }
	    }
	    $num = $total/10;
	    $num = int($num);
	    $num = ($num+1)*10;
	    $num = $num-$total;	    
	    if( $num == $id[9] ){
	    	print "La cedula es correcta\n";
	    }  
	}else{
		print "no es el tamaño de la cedula\n";
	} 	
}
