#Jest to kontynuacja kursu (cz. 2) Ruby in Twenty Minutes


#1. Stringi
#Wszystkie metody jakie mozemy wywolac na Stringach sprawdzamy poleceniem
#String.methods

"Kot w butach".methods.size 	# 162 (tyle jest metod na stringach)

"Kot w butach".upcase		# "KOT W BUTACH"

"Kot w butach".downcase		# "kot w butach"

"%s w butach" % "Kot"		# "Kot w butach"

"%f w butach" % 2.72		# "2.720000 w butach"

"%0.1f w butach" % 2.72		# "2.7 w butach"

"Kot w butach".size		# 12

"Kot w butach".split(' ')	# ["Kot", "w", "butach"]

"Kot;w;butach".split(';')	# ["Kot", "w", "butach"]

"Kot-w;butach".split(/[;-]/)	# # ["Kot", "w", "butach"] (wyrażenie reg. dziel wzgledem ';' lub '-')

"123".to_i + 2 			# 125

"Ala ma " + 5.to_s + " ciastek"	# "Ala ma 5 ciastek"

#2. Tablice

tablica = [3,2,4,1,5]		# [3, 2, 4, 1, 5]
tablica.max			# 5
tablica.min			# 1
tablica.first			# 3
tablica.last			# 5
tablica.sort 			# [1, 2, 3, 4, 5]
tablica + [10, 11, 20]		# [3, 2, 4, 1, 5, 10, 11, 20]
tablica[1, 3]			# [2, 4, 1]
# wyswietlanie tablicy z kazdym potrojonym elementem:
tablica.each {|i| puts i*3}
# funkcja mapujaca tablice, ale ona nie zmienia tablicy oryginalnej, tylko wyswietla w tym wypadku pomnozona przez 2
tablica.map {|i| i*2 } 		# [6, 4, 8, 2, 10]
#dopiero funkcje z '!' zmieniaja wartosc oryginalnej tablicy, np.
tablica.map! {|i| i*1.5 }	# [4.5, 3.0, 6.0, 1.5, 7.5]
# tablice nie musza sie skladac tylko z liczb, mozna sobie zadeklarowac np.
a = ["kot", 1.2, nil, [1,2,3]]  # ["kot", 1.2, nil, [1,2,3]]
# wybieranie liczb z naszej tablicy, np. mniejszych od 5
tablica.select {|i| i < 5}	# [4.5, 3.0, 1.5]

#3. Hasze

zw_wl = {jacek: 'pies', adam: 'kot'} 	# {:jacek=>"pies", :adam=>"kot"}
zw_wl[:adam]				# kot
zw_wl.keys				#  [:jacek, :adam]
zw_wl.values				# ["pies", "kot"]
zw_wl.to_a				#[[:jacek, "pies"], [:adam, "kot"]]
zw_wl[:aga] = 'chomik'
zw_wl					# {:jacek=>"pies", :adam=>"kot", :aga=>"chomik"}

zw_wl.each { |klucz, wartosc| puts "#{klucz} => #{wartosc}" }	
							# jacek => pies
							# adam => kot
							# aga => chomik
#4. Czas i data
Time.now				# 2014-11-16 21:54:51 +0100
Time.now + 10				#dodaje 10 sekund do obecnego czasu
Time.now.hour				# 21
Time.now.month				# 11
Time.now.monday?			# false

#Aby operowac na datach musimy wczytac biblioteke poleceniem:
require 'date'
Date.today.to_s				# "2014-11-16"
(Date.today + 10).to_s			# "2014-11-26"



