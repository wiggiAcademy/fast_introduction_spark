# Unir datasets para leerlos con spark
paste X_test.txt y_test.txt > test.txt
awk 'function trim(field){
   gsub(/(\de[-+]\d)|[^-+0-9.]/gi, field); 
   return field
   }
   {getline f1 < "y_test.txt" ; printf "%s%s",trim(f1),trim($0)}

 ' X_test.txt > test.txt

awk 'function trim(field){
   gsub(/(\de[-+]\d)|[^-+0-9.]/gi, field); 
   return field
   }
   {getline f1 < "y_train.txt" ; printf "%s%s",trim(f1),trim($0)}

 ' X_train.txt > train.txt