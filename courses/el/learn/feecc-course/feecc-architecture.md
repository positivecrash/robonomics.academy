---
title: "Αρχιτεκτονική"
description: Αυτό το μάθημα αφορά την εξοικείωση με το σύστημα Feecc και όλα τα στοιχεία του.
metaOptions: [Μάθετε, Εξοικειωθείτε με το Feecc]
defaultName: Getting Used to Feecc
---

<RoboAcademyText fWeight="500">
Σε αυτό το μάθημα, θα εξετάσουμε πιο από κοντά την αρχιτεκτονική του Feecc και θα εξετάσουμε όλα τα στοιχεία του λογισμικού.
</RoboAcademyText>

Η πλατφόρμα Feecc αποτελείται από αρκετές υπηρεσίες, από τον έλεγχο του εργαλείου μηχανικού έως την παροχή αναλύσεων. Κάθε υπηρεσία είναι υπεύθυνη για κάποιο είδος λειτουργικότητας που απαιτείται για την ανάπτυξη σε ένα επιχειρηματικό περιβάλλον.

## Εργαλείο Μηχανικού Feecc

Η κύρια εργασία του Εργαλείου Μηχανικού είναι να οργανώσει τον χώρο εργασίας του μηχανικού συναρμολόγησης. Ανάλογα με την εργασία, ο μηχανικός μπορεί να χρειαστεί τις ακόλουθες συσκευές:

- Κάμερα IP για την οργάνωση της βιντεοσκόπησης της διαδικασίας παραγωγής·
- Αναγνώστη RFID για την ταυτοποίηση στο σύστημα με την προσωπική κάρτα RFID·
- Αναγνώστη barcode για τη σάρωση ετικετών προϊόντων·
- Εκτυπωτή ετικετών για την επισήμανση των κατασκευασμένων προϊόντων·
- Ψηφιακοί αισθητήρες που συλλέγουν δεδομένα από διάφορες συσκευές / σταθμούς.

Το λογισμικό του Εργαλείου Μηχανικού αποτελείται συνήθως από τα ακόλουθα δοχεία. Πρώτον, το λογισμικό που απαιτεί εγκατάσταση **στον υπολογιστή στον οποίο εργάζεται ο υπάλληλος** κατά τη συναρμολόγηση του προϊόντος:

1. [feecc-workbench-daemon](https://github.com/Multi-Agent-io/feecc-workbench-daemon) — η καρδιά της πλατφόρμας Feecc που παρέχει στους χρήστες πρόσβαση σε όλες τις λειτουργίες και ρυθμίσεις του Feecc· περιλαμβάνει επίσης ελαφριές υπηρεσίες για εκτύπωση ετικετών χρησιμοποιώντας εκτυπωτή ετικετών και εγγραφή βίντεο από ροές RTSP·
2. [feecc-workbench-frontend](https://github.com/Multi-Agent-io/feecc-workbench-frontend) — μια διαδικτυακή διεπαφή για την αλληλεπίδραση του υπαλλήλου με την πλατφόρμα Feecc·
3. [feecc-hid-reader-daemon](https://github.com/Multi-Agent-io/feecc-hid-reader-daemon) — ένας δαίμονας Python για την αποστολή συμβάντων USB περιφερειακών·

Δεύτερον, το λογισμικό που μπορεί να εγκατασταθεί **τόσο στον υπολογιστή του υπαλλήλου όσο και σε ένα διακομιστή στο τοπικό δίκτυο**:

1. [feecc-ipfs-gateway](https://github.com/Multi-Agent-io/feecc-ipfs-gateway) — ένα microservice για τη δημοσίευση αρχείων στο IPFS, και πιο συγκεκριμένα, τα CID αρχείων στο Δίκτυο Robonomics;

Η παρακάτω εικόνα δείχνει την αρχιτεκτονική του Χώρου Εργασίας Μηχανικού του Feecc σε εταιρικό περιβάλλον. Η IPFS Gateway (καθώς και το IPFS node και το MongoDB σε μορφή cluster peer) μπορεί να φιλοξενηθεί σε κάθε υπολογιστή του εργαζομένου, το οποίο θα ενισχύσει την αποκεντρωτοποίηση του συστήματος με κόστος υπολογιστικών πόρων;

<LessonImages src="feecc-course/feecc_global_hardware.png" alt="an architecture of Feecc"/>

### Υποστηριζόμενος εξοπλισμός για έναν χώρο εργασίας:

#### Αναγνώστης RFID

Ένας USB αναγνώστης RFID απαιτείται για την εξουσιοδότηση των μηχανικών στον τομέα με τις εσωτερικές τους κάρτες. Η εισερχόμενη πληροφορία επεξεργάζεται χρησιμοποιώντας το `feecc-hid-reader-daemon`.

#### Αναγνώστης Barcode

Ο USB αναγνώστης barcode είναι απαραίτητος για την αναγνώριση προϊόντων με βάση τους κωδικούς τους, την αποστολή εντολών σε υπηρεσίες και για τη σωστή ανάθεση πιστοποιητικών. Η εισερχόμενη πληροφορία επεξεργάζεται επίσης με το `feecc-hid-reader-daemon`. Η ανάγνωση σε δύο διαστάσεις είναι επιθυμητή, αλλά όχι απαραίτητη.

#### Υπολογιστής του εργαζομένου

Ένα μικρό μονοπλακέ υπολογιστή επεξεργάζεται τα σήματα από εξωτερικές συσκευές (αναγνώστης barcode, αναγνώστης RFID), στέλνει αιτήματα για εκτύπωση εικόνων στον εκτυπωτή, ξεκινά και σταματά την εγγραφή βίντεο, στέλνει δεδομένα στην IPFS Gateway. Τρέχει τις ακόλουθες υπηρεσίες: `feecc-workbench-frontend`, `feecc-workbench-daemon` με υποστήριξη εκτυπωτή ετικετών και κάμερας, `feecc-hid-reader-daemon`. Απαιτείτι σύνδεση στο Internet μέσω Wi-Fi ή LAN.
    
Αξίζει να αναφερθεί ότι οποιοσδήποτε υπολογιστής μπορεί να χρησιμοποιηθεί αντί για έναν μονοπλακέ υπολογιστή με οθόνη. Το λειτουργικό σύστημα GNU/LINUX πρέπει να είναι εγκατεστημένο είτε φυσικά είτε μέσω εικονικής μηχανής.
    
Ελάχιστες τεχνικές προδιαγραφές:
    
- Επεξεργαστής: Broadcom BCM2711, Quad core Cortex-A72 (ARM v8) 64-bit SoC @ 1.8GHz ή παρόμοιος;
- RAM: 4GB LPDDR4-3200 ή παρόμοιο.

#### Οθόνη

Η οθόνη χρησιμοποιείται από τον υπάλληλο για την εισαγωγή και προβολή πληροφοριών σχετικά με το τρέχον στάδιο παραγωγής. Επίσης εμφανίζει υποδείξεις για τον μηχανικό σχετικά με το τρέχον στάδιο. Μπορούν επίσης να χρησιμοποιηθούν και άλλες συσκευές εισόδου.

#### Εκτυπωτής ετικετών

Ο εκτυπωτής ετικετών χρησιμοποιείται για την εκτύπωση κωδικών QR και bar για την περαιτέρω τοποθέτηση ετικετών στο προϊόν για σκοπούς αναγνώρισης και επαλήθευσης. Η αλληλεπίδραση με τον εκτυπωτή γίνεται με τη βοήθεια της αντίστοιχης υπηρεσίας `feecc-workbench-daemon`. Στην περίπτωσή μας χρησιμοποιούμε εκτυπωτές XPrinter 236B.

#### Κάμερα IP

Κάμερα IP για την καταγραφή των διαδικασιών παραγωγής για συμπερίληψη στο πιστοποιητκό προϊόντος. Βρίσκεται πάνω από την περιοχή συναρμολόγησης του προϊόντος. Η αλληλεπίδραση με την κάμερα γίνεται με τη χρήση της αντίστοιχης υπηρεσίας `feecc-workbench-daemon`.

Απαιτούμενες τεχνικές προδιαγραφές: Παροχή ισχύος PoE, πρωτόκολλο μεταφοράς δεδομένων RTSP. Στην περίπτωσή μας χρησιμοποιούμε κάμερες Hikvision HiWatch DS-i200d.

### Υποστηριζόμενος εξοπλισμός για αρκετούς χώρους εργασίας:

#### Δρομολογητής ή switch

Απαιτείται δρομολογητής ή switch με υποστήριξη PoE 802.3af και τροφοδοσία PoE στις έξοδοι για την τροφοδότηση των καμερών IP και τη σύνδεσή τους με την υπηρεσία `feecc-workbench-daemon`. Στην περίπτωσή μας χρησιμοποιούμε το MikroTik hEX PoE (ένας για 3-4 χώρους εργασίας) και τροφοδοτικό.

#### Διακομιστής (προαιρετικό)

Μπορεί επίσης να εγκατασταθεί ένας μεγαλύτερος διακομιστή που μπορεί να εκτελέσει το `feecc-ipfs-gateway`. Μπορεί να βρίσκεται στη θέση ενός από τους υπολογιστές των χώρων εργασίας των υπαλλήλων. 

Ελάχιστες τεχνικές προδιαγραφές:

- Επεξεργαστής: Intel Xeon E-2200 ή παρόμοιος;
- RAM: 8GB;
- Αποθήκευση: 1TB HDD;
- Διεπαφή LAN: 1 Gbit/s.

## Ανάλυση Feecc

Ο κύριος στόχος της Ανάλυσης Feecc είναι να οργανώσει τη διαδικασία της ανιχνευσιμότητας των τελικών προϊόντων και τους προ-πωλητικούς έλεγχους τους στο τμήμα ελέγχου προϊόντων.

Η Ανάλυση Feecc εξαρτάται από τα ακόλουθα containers:

1. [feecc-analytics-backend](https://github.com/Multi-Agent-io/feecc-analytics-backend) — το κύριο λογισμικό για την ανάπτυξη υπηρεσίας αναλυτικών;
2. [feecc-analytics-frontend](https://github.com/Multi-Agent-io/feecc-analytics-frontend) — το λογισμικό frontend για την υπηρεσία αναλυτικών;

Συνήθως αναπτύσσεται σε έναν μόνο διακομιστή τοπικά για λόγους ασφάλειας δεδομένων μέσα μόνο στον οργανισμό.

Το υλικό που απαιτείται για τη λειτουργία της Ανάλυσης Feecc είναι ένας τοπικός ή απομακρυσμένος διακομιστής (εικονική μηχανή) στον οποίο θα τρέχει η web εφαρμογή και ο αναγνώστης barcode. Κάθε εξουσιοδοτημένος υπάλληλος μπορεί να έχει πρόσβαση στη web εφαρμογή από τον υπολογιστή του με ένα όνομα χρήστη και κωδικό πρόσβασης.

## Επικυρωτής Feecc

Ο κύριος στόχος του Επικυρωτή Feecc είναι να συγκρίνει δεδομένα από διαφορετικά αποθηκευτικά μέσα για να επιβεβαιώσει την ακεραιότητα του ψηφιακού πιστοποιητικού προϊόντος.

Ο Επικυρωτής Feecc εξαρτάται από τα ακόλουθα containers:

1. [feecc-validator-backend](https://github.com/Multi-Agent-io/feecc-validator-backend) — ένα microservice, σχεδιασμένο για την χειρισμό της επικύρωσης πιστοποιητικών και την ανάκτηση δεδομένων που σχετίζονται με τη μονάδα που παρέχει ο χρήστης έχει μόνο ένα από τα κομμάτια δεδομένων;
2. [feecc-validator-frontend](https://github.com/Multi-Agent-io/feecc-validator-frontend) — μια διεπαφή web για αλληλείδραση με το microservice επικύρωσης.

Όπως και η Ανάλυση Feecc, μπορεί να αναπτυχθεί σε έναν μόνο διακομιστή τοπικά και απαιτεί αναγνώστη barcode.

<RoboAcademyText fWeight="500">
Στο επόμενο μάθημα, θα εξετάσουμε πιο αναλυτικά το σύστημα Feecc μέσω μιας μικρής επίδειξης που τρέχει τοπικά στον υπολογιστή σας.
</RoboAcademyText>