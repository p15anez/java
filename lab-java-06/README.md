### Εργαστήριο #5-6-7 - Κλάσεις, μέθοδοι, static μέλη, απαριθμήσεις, _διεπαφές_
___
Σκοπός του έκτου εργαστηρίου είναι να εξοικειωθείτε περαιτέρω με τη χρήση συλλογών, να αξιοποιήσετε απαριθμήσεις και _να υλοποιήσετε διεπαφές_.

___
#### Άσκηση #### (_δείτε πιο κάτω για εργαστήριο 6 & 7_)
Σε αυτό το εργαστήριο θα πρέπει να δημιουργήσετε  επεκτείνουμε τη
Δημιουργήσετε μια κλάση σε γλώσσα `java` η οποία να αναπαριστά παραγγελίες αντικειμένων για κάποια επιχείρηση. Ονομάστε την κλάση σας `Order`.

Η κλάση σας να περιέχει __τα ακόλουθα πεδία δεδομένων__:
* `itemName` τύπου `String` το οποίο αποθηκεύει την ονομασία του προϊόντος
* `netValue` τύπου `double` το οποίο αποθηκεύει την τιμή μονάδας ενός προϊόντος, προφανώς μεγαλύτερη ή ίση του μηδενός
* `quantity` τύπου `int` το οποίο αποθηκεύει την ποσότητα ενός προϊόντος, προφανώς μεγαλύτερη ή ίση του μηδενός, `default` τιμή `1`
* `discount` τύπου `double` το οποίο αποθηκεύει ενδεχόμενο ποσοστό έκπτωσης, `default` τιμή `0.0`, αποδεκτές τιμές μεταξύ 0.0 και 1.0 (=100%).

Όλα τα στιγμιότυπα της κλάσης θα πρέπει να μοιράζονται την κοινή static μεταβλητή `vat` τύπου `double` με τιμή `0.23` (=23%)

H κλάση σας θα πρέπει να παρέχει __τους ακόλουθους constructor__, αλλά όχι __default constructor__:
* `constructor` με δύο παραμέτρους, την `ονομασία προϊόντος` και την `τιμή μονάδας`, τα υπόλοιπα μελη κρατούν τις default τιμές τους
* `constructor` με τρεις παραμέτρους, την `ονομασία προϊόντος`, την `τιμή μονάδας` και την `ποσότητα`, τα υπόλοιπα μελη κρατούν τις default τιμές τους
* `constructor` με τέσσερις παραμέτρους, την `ονομασία προϊόντος`, την `τιμή μονάδας`, την `ποσότητα` και ένα `ποσοστό έκπτωσης`

Η κλάση σας θα πρέπει επιπλέον να παρέχει μια μέθοδο `computeBill` η οποία δε δέχεται παραμέτρους και με βάση τις τιμές των μελών δεδομένων του αντικειμένου υπολογίζει το πληρωτέο ποσό.

Επιπλέον η κλάση σας να παρέχει υπερφορτωμένες μεθόδους `toString()` και `equals()`, η πρώτη να παρέχει μια `String` αναπαράσταση της παραγγελίας, η δεύτερη να συγκρίνει δύο παραγγελίες για ομοιότητα. Κριτήριο ομοιότητας είναι η ομοιότητα του `itemName` και η ισότητα του `netValue`.

Τέλος, αξιοποιώντας όλα τα παραπάνω, εντός της `main` της κλάσης να υλοποιήσετε διαλογικό με το χρήστη πρόγραμμα (θυμηθείτε τη Scanner) στο οποίο ο χρήστης να δημιουργεί νέες παραγγελίες. Κάθε παραγγελία να εισάγεται σε μια `λίστα`, αφού πρώτα έχει γίνει έλεγχος αν υπάρχει άλλη _όμοια_ παραγγελία. Αν υπάρχει, αντί εισαγωγής να κάνετε ενημέρωση της παραγγελίας που ήδη υπάρχει συμψηφίζοντας τις ποσότητες και κρατώντας την καλύτερη έκπτωση.

Με την ολοκλήρωση της παραγγελίας (όπως αποφασίσετε να γίνεται αυτό) να υπολογίζεται και να εμφανίζεται το συνολικό ποσό και καθένα `Order`.

### Εργαστήριο 6
Δημιουργήστε μια απαρίθμηση (enumeration) η οποία να περιέχει ως σταθερές τους διάφορους τύπους πληρωμής που μπορεί να αξιοποιήσει ένας πελάτης για την πληρωμή, κάθε τύπος μπορεί να έχει ένα ποσοστό χρέωσης συναλλαγής και ένα ελάχιστο ποσό χρεώσης συναλλαγής. Αυτά τα ποσά παρακρατούνται από τα έσοδα της εταιρίας, σκοπός λοιπόν είναι να ελαχιστοποιούνται προτείνοντας στο πελάτη τρόπους πληρωμής με αυξανόμενο κόστος για την εταιρία (δλδ πρώτα οι πιο οικονομικοί για την εταιρία τρόποι). Για κάθε τρόπο πληρωμής, όμως μπορεί να υπάρχει και μέγιστο επιτροπόμενο ποσό συναλλαγής.


| Τύπος πληρωμής | Ποσοστό χρέωσης | Ελάχιστο ποσό χρεώσης | Μέγιστο ύψος συναλλαγής |
| -------------- | ---------------:| ---------------------:| -----------------------:|
| Cash | - | - | 300.0 |
| Debit Card | 2% | 1.0 | 2,000.0 |
| Credit Card | 1.5% | 2.0 | 2,000.0 |
| Bank Transfer | - | 3.0 | 10,000.0 |

Η απαρίθμηση που θα υλοποιήσετε να ονομάζεται `PaymentMethod`, να ενσωματώνει τον πιο πάνω πίνακα ποστών χρεώσεων και να παρέχει μέθοδο `double calculateTransactionFee(double amount)` η οποία λαμβάνοντας ένα ποσό πληρωμής επιστρέφει τη χρεώση συναλλαγής (για τον αντίστοιχο τύπο συναλλαγής). _Καθώς δε γνωρίζουμε ακόμη exceptions, σε περίπτωση που το ποσό (amount) ξεπερνά το μέγιστο επιτρεπόμενο ύψος συναλλαγής, η μέθοδος επιστρέφει το ίδιο το ποσό και εμφανίζει ένα μήνυμα ότι η συναλλαγή δεν είναι επιτρεπτή_.

Εξελίξτε τη μέθοδο `main` του προηγούμενου εργαστηρίου, έτσι ώστε μετά την ολοκλήρωση της καταγραφής της παραγγελίας, να εμφανίζεται πρώτα το συνολικό οφειλόμενο ποσό και μετά να εμφανίζονται με αύξουσα σειρά (ως προς το κόστος για την εταιρία) οι επιλογές τρόπου πληρωμής. Προφανώς αγνοούνται τρόποι πληρωμής που έχουν για την εταιρία κόστος μεγαλύτερο από τα έσοδά της (καθαρό ποσό, χωρίς το ΦΠΑ). Για την προβολή των προτεινόμενων `PaymentMethod`s αξιοποιήστε κατάλληλο `Map` collection το οποίο να σας εξασφαλίζει ταξινόμηση με αυξανόμενο κόστος.

### Εργαστήριο 7
Τροποποιήστε την πιο πάνω κλάση, έτσι ώστε να υλοποιεί (implement) το Comperable Interface (public interface `java.lang.Comparable<T>`) τη γλώσσας προγραμματισμού Java.
Για να το πετύχετε αυτό θα πρέπει να υλοποιήσετε εντός της κλάσης Order μέθοδο:

Τροποποιήστε στη συνέχεια το πρόγραμμα που έχετε γράψει εντός της `main` του εργατηρίου 6, ώστε (αφού ελέγξετε εάν υπάρχει όμοια παραγγελία, οπότε κάνετε την απαραίτητη συγχώνευση) να εισάγετε όλες τις παραγγελίες σε κατάλληλο `Collection` ώστε να εμφανίζονται ταξινομημένες με αύξουσα αξία.
Hint: χρησιμοποιήστε μια Tree δομή και όταν χρειάζεται να διατρέξετε τη δομή χρησιμοποιήστε ένα Iterator.