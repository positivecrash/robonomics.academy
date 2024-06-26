---
title: "Συναρμολόγηση Έξυπνου Συστήματος Σπιτιού"
lastUpdate: Thu May 18 2023 10:46:29 GMT+0400 (Samara Standard Time)
description: Θα μάθετε πώς να συναρμολογήσετε το έξυπνο σύστημα σπιτιού!
metaOptions: [Μάθετε]
defaultName: Introduction to open source solution for private smart homes
---

<LessonImages imageClasses="mb" src="smart-home-intro/spring-school-2023-smart-stand-intro.gif" />

## Πίνακας Έξυπνου Σπιτιού 

Αυτό το πάνελ προορίζεται για χρήση ως συσκευή κεντρικού ελέγχου με τα πιο συχνά χρησιμοποιούμενα διακόπτες και δεδομένα που εμφανίζονται σε αυτό. Επίσης είναι δυνατή η σύνδεση ενός εσωτερικού τηλεφώνου και η χρήση του ως εσωτερικός παρακολουθητής. Βασικά είναι απλά ένα tablet που τρέχει το λειτουργικό σύστημα Android στην περίπτωσή μας. Το μόνο που χρειάζεται να κάνετε είναι να παρέχετε ρεύμα. Νομίζουμε ότι αυτό το πάνελ θα έπρεπε να εγκατασταθεί εκεί όπου θα τοποθετούσατε έναν εσωτερικό παρακολουθητή

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcbdAJqbwHAQ3NeyWQUwSoS4drDexa3AEs7HXuM1BrUT1', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-1.png" />


## Διακόπτης Φωτός

Οι έξυπνοι διακόπτες φωτός μοιάζουν περισσότερο ή λιγότερο με τους συνηθισμένους, εκτός από το γεγονός ότι χρησιμοποιούνται πλήκτρα πίεσης αντί για διακόπτες. Ένα πλήκτρο πίσης επιστρέφει στη θέση του μετά το πάτημα. Δεν υπάρχει διαφορά στη σύνδεση μεταξύ ενός κανονικού διακόπτη και ενός έξυπνου: συνδέστε τον ουδέτερο αγωγό στο N, τον αγωγό ρεύματος στο L και τη γραμμή φωτισμού στο L1. Μετά τη συναρμολόγηση του διακόπτη για να τον συνδέσετε μέσω ZigBee, πιέστε το κουμπί για τουλάχιστον 5 δευτερόλεπτα.

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/Qmb138DiQWWBgowMj2fC9kmiGYh9WEeytteSkqumWCv2LB', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-2.png" />

Στην περίπτωση του διακόπτη με δύο κουμπιά (ή περισσότερα), η μόνη διαφορά είναι η δεύτερη (τρίτη, ...) γραμμή φώτων. 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZiStYZG4rmyNPXXmCXsVPm7witPpnNJMBzD8GtxedgPo', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-3.png" />

## Έξυπνη λάμπα 

Οι έξυπνες λάμπες είναι πιθανότατα ο πιο εύκολος τρόπος για να δοκιμάσετε κάτι έξυπνο, δεν χρειάζεται καν να είστε ηλεκτρολόγος. Μπορούν να ελέγχονται απομακρυσμένα και να αλλάζουν τη φωτεινότητά τους ή το χρώμα τους. Μπορείτε να τις εγκαταστήσετε μαζί με έξυπνους διακόπτες ή ξεχωριστά. Χρησιμοποιώντας τέτοιες συσκευές μπορείτε να ανοίξετε μια ολόκληρη σελίδα αυτοματισμών ανάλογα με τη διάθεσή σας ή τις εξωτερικές συνθήκες! Οι νέες λάμπες είναι έτοιμες να συνδεθούν μέσω ZigBee. Σε περίπτωση που δεν μπορείτε να βρείτε μία, αλλάξτε την 5 φορές on και off


<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbiMHLJqnDpr1Whzvo6Y7zE33cQPuTs7furbt3JW2uiek', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-4.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmTzK4dY168HVgLvVBsRxR4M4vda55XC7pFhpW5kRexujQ', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-5.png" />

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZFpvVUavKc1Za9SeXqikrfySsfFHuVrkdzgbVB8um7T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-6.png" />

## Έξυπνη πρίζα 

Υπάρχει μια σειρά από συσκευές που δεν είναι έξυπνες και συνήθως χρειάζεται να τις ενεργοποιούμε και να τις απενεργοποιούμε καμιά φορά. Αν ενεργοποιήσουμε μια τέτοια συσκευή μέσω της έξυπνης πρίζας, μπορούμε να την ενεργοποιούμε/απενεργοποιούμε ανάλογα με τις ανάγκες μας, το πρόγραμμα ή τις συνθήκες. Επίσης, τέτοιες πρίζες μπορούν να παρακολουθούν την κατανάλωση ενέργειας, έτσι έχουμε δεδομένα για το πόση ενέργεια καταναλώνει αυτή η συσκευή. Η σύνδεση είναι αρκετά εύκολη, για να συνδέσετε την έξυπνη πρίζα, πιέστε το κουμπί για 5 δευτερόλεπτα

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRtmKXSv7csHLbKVuZkoA5Eb2zyTkEAbUxLYT6Qt1yxZH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-7.png" />

## Διακόπτης Λέβητα 

Ο λόγος που ο διακόπτης λέβητα υπάρχει ως αφιερωμένη συσκευή είναι ότι μπορεί να υποστηρίξει μεγαλύτερο φορτίο. Συνήθως οι λέβητες καταναλώνουν 3kWh ή ακόμα και περισσότερο, οπότε οι κανονικοί (ακόμα και έξυπνοι) διακόπτες δεν είναι κατάλληλοι σε αυτήν την κατάσταση. Ο διακόπτης λέβητα είναι σχεδιασμένος να λειτουργεί υπό αυτές τις συνθήκες. Οι συνδέσεις και ο συνδυασμός είναι σχεδόν ίδιοι με αυτούς του διακόπτη φωτός

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmNZyRtXXRYCrAQe6s6ZFJLXtUrH7SZHJC1Bt61kTrRX54', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-8.png" />

## Wifi/Zigbee Thermostat

Μοιάζει με έναν συνηθισμένο θερμοστάτη αλλά έχει τη δυνατότητα να ελέγχεται ασύρματα. Υπάρχουν επιλογές: συνδέστε ένα σύστημα θέρμανσης απευθείας στο θερμοστάτη ή χωρίστε τα. Στη δεύτερη περίπτωση, ο θερμοστάτης θα μας πει τη λειτουργία (θέρμανση, ψύξη, ανεμιστήρας, κλπ) και τη θερμοκρασία

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRjxo9EGUvQiMm84xvXCL6LfrQJYza71vmFsa9Zpy7qmz', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-9.png" />

## Curtain Switch

Ένας ακόμα αφιερωμένος διακόπτης, αυτή τη φορά για κουρτίνες. Από τεχνική άποψη δεν είναι απαραίτητο να χρησιμοποιήσουμε αυτόν τον διακόπτη μόνο, θα μπορούσαμε να χρησιμοποιήσουμε οποιονδήποτε τριπλό διακόπτη και να τον συνδέσουμε στον κινητήρα της κουρτίνας, αλλά αυτός έρχεται με ειδικά εικονίδια. Για να συνδέσετε τον διακόπτη, πατήστε παρατεταμένα το κουμπί στη μέση

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmRpEpZbyNkzby8Sk22Ymz59DbAcnty1B1osWc2kZr5FZ7', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-10.png" />

## Smart Valve Controller

Επιλέξτε έναν ελεγκτή ανάλογα με τις βαλβίδες που έχετε. Το πιο προφανές σενάριο είναι να συνδυάσετε αυτόν τον ελεγκτή με έναν αισθητήρα διαρροής νερού. Για να συνδέσετε τη συσκευή, κρατήστε πατημένο το κουμπί για 5 δευτερόλεπτα

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmcjZcJ6P8Q5yUfSRx8R2mR4A7r2fi5bLs5uoUr3EAXLZs', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-11.png" />

## Water Leakage Sensor

Ένα αρκετά απλό μηχάνημα που στέλνει σήμα όταν οι δύο επαφές του συνδέονται. Το νερό μεταφέρει ηλεκτρισμό και όταν υπάρχει νερό κάτω από τον αισθητήρα, οι επαφές του κλείνουν. Ο αισθητήρας λειτουργεί με μπαταρία και συνήθως διαρκεί 1-2 χρόνια. Για να συνδέσετε τον αισθητήρα μέσω ZigBee, πατήστε παρατεταμένα το κουμπί του για λίγο 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmbgetJK1E8qQMcnBVREutpy8tKfbesqaxXiebjzpoyrdV', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-12.png" />

## IR Controller

Σκεφτείτε το ως το τηλεχειριστήριο τηλεόρασης σας... αλλά έξυπνο! Και δεν περιορίζεται στην εργασία με τηλεοράσεις μόνο. Αν ο κλιματιστικός σας έχει τηλεχειριστήριο, μπορεί να αντικατασταθεί με αυτό το έξυπνο. Για να το συνδέσετε, πατήστε το κουμπί επαναφοράς στο πίσω μέρος του ελεγκτή για λίγο. Υπάρχουν πολλές βιβλιοθήκες με έτοιμες εντολές χρήσης, για παράδειγμα [https://github.com/smartHomeHub/SmartIR](https://github.com/smartHomeHub/SmartIR). Το μόνο που χρειάζεται να κάνετε είναι να βρείτε το μοντέλο της τηλεόρασης ή του κλιματιστικού σας

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmVjj92fMLbA6QJ5QhnmiqBT1huD5b7xyfi3VadHFDYwtm', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-13.png" />

## Door/Window Sensor

Ένας ακόμα αισθητήρας που λειτουργεί με μπαταρία αλλά βοηθά στη δημιουργία ενός απλού συστήματος ασφαλείας ή στη σύνδεσή του με φώτα και άλλες συσκευές. Για να το συνδέσετε μέσω ZigBee, βάλτε ένα βελάκι στην τρύπα και πιέστε το για λίγο

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmZyb66dKEqk9iCVKhaBk5ZKASi7dXdFSg2CBXY1fwuu5J', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-14.png" />

## Motion Sensor
Το ίδιο με τον αισθητήρα πόρτας/παραύρου, μπορεί να χρησιμοποιηθεί σε διάφορα σενάρια. Τα πιο προφανή είναι ο έλεγχος των φώτων ή η ανίχνευση κινήσεων όταν είστε μακριά

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmUA7TLg12pkhkbdGH6fwNDasU1kiyLHBJSutA2YG71Mka', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-15.png" />


## Temperature & Humidity Sensor

Είναι καλό να γνωρίζετε τις συνθήκες στις οποίες ζείτε, σωστά; Αυτός ο αισθητήρας θα σας παρέχει μετρήσεις θερμοκρασίας και υγρασίας. Έπειτα μπορείτε να χρησιμοποιήσετε αυτά τα δεδομένα για να ανοίξετε/κλείσετε το κλιματιστικό σας ή άλλα συστήματα θέρμανσης/ψύξης. Για να συνδέσετε τον αισθητήρα, υπάρχει ένα κουμπί στο πίσω μέρος 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmayYFowfJVwQBVxPUSvi5inedqKzhyRZXp8fBUUayJnqH', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-16.png" />

## Security Camera

Στο τέλος είναι καλό να ρίξετε μια ματιά σε τι συμβαίνει στο σπίτι σας. Μια καλή αυτοματοποίηση θα ήταν να συνδέσετε τον αισθητήρα κίνησης με την κάμερα, έτσι θα έχετε ένα βίντεο διάρκειας 10 δευτερολέπτων όταν ανιχνευθεί κίνηση 

<LessonVideo :videos="[{src: 'https://crustipfs.info/ipfs/QmX8nnDCgTx2kuwfAGv6B4orkEg4w6phtJtxSp44HfdD9T', type: 'webm'}]" cover="smart-home-intro/assembling-smart-home-board-17.png"  />


## Smart Board 
Ρίξτε μι ματιά στα αποτελέσματα [https://www.youtube.com/watch?v=B3er7bwtvkw](https://www.youtube.com/watch?v=B3er7bwtvkw )
Και παίξτε με αυτό μόνοι σας [https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20](https://twitter.com/vadim_manaenko/status/1653777703718334469?s=20)

