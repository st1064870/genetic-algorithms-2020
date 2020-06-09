---
puppeteer:

        format: A4
        displayHeaderFooter: false
        margin:
            top: 1cm
            right: 1cm
            bottom: 1cm
            left: 1cm
---

<center><h2>Project Yπολογιστικής Νοημοσύνης</h2></center>
<center><h3>Γενετικοί Αλγόριθμοι</h3></center>
<center><h4>Θεόδωρος Συμεωνίδης Α.Μ. 1064870<h4></center>

<div style="page-break-after: always;"></div>

### Πίνακας περιεχομένων

[TOC]

<div style="page-break-after: always;"></div>

----------------------------------------------

Το αποθετήριο του κώδικα στο Github βρίσκεται [εδώ](https://github.com/st1064870/genetic-algorithms-project-2020)

----------------------------------------------
### Β1. Σχεδιασμός ΓΑ
#### α) Κωδικοποίηση
> Να προτείνετε μια κωδικοποίηση για τα άτομα του πληθυσμού

Το κάθε άτομο θα αποτελείται από μια λίστα (διάνυσμα) με 1682 ακέραιους που ανήκουν στο διάστημα [1, 5], δηλαδή με τις αξιολογήσεις του για κάθε ταινία .

#### β) Πλεονάζουσες τιμές
> Είναι πιθανό να προκύψουν πλεονάζουσες τιμές, για παράδειγμα, τιμές > 5 λόγω δυαδικής κωδικοποίησης. Περιγράψτε πώς θα αντιμετωπίσετε το πρόβλημα αυτό. 

Με την συγκεκριμένη κωδικοποίηση δεν είναι πιθανό να προκύψουν πλεονάζουσες τιμές.

> Εξετάστε αν μπορείτε να αποφύγετε τις πλεονάζουσες τιμές, αναθεωρώντας την κωδικοποίηση που προτείνατε στο (α)

Δεν χρειάζεται αναθεώρηση τις κωδικοποίησης.

#### γ) Αρχικός πληθυσμός
Η διαδικασία που θα ακολουθήσουμε για τη δημιουργία του αρχικού πληθυσμού είναι η εξής. Επιλέγουμε έναν χρήστη (διάνυσμα γραμμή) από τον 943x1682 πίνακα του ml100k datashet. Αυτό θα έχει κάποιες κενές τιμές στις ταινίες που δεν έχει αξιολογήσει ο χρήστης.

> Τι είδους αρχικές τιμές θα επιλέξετε για τις ταινίες που δεν έχει δει ο χρήστης; Μπορεί να αντιστοιχούν στο μέσο όρο, όπως στο μέρος Α;

Για τη δημιουργία του πληθυσμού θα βασιστούμε στο διάνυσμα που επιλέξαμε παραπάνω και τις κενές τιμές θα τις γεμίσουμε με τυχαίες τιμές Προφανώς δεν μπορούμε να τις γεμίσουμε με τον μέσω όρο των βαθμολογιών του χρήστη αφού ο αρχικός πληθυσμός θα αποτελούταν από ίδια άτομα, θα μπορούσαμε όμως να προσθέταμε σε αυτόν τον μέσω όρο ένα μικρό ποσό θορύβου ώστε να πέρναμε διαφορετικά άτομα. Ωστόσο πιστεύουμε πως ακόμα και μετά αυτό το τέχνασμα ο αρχικός υποχώρος στον οποίο θα ψάξουμε για λύσεις είναι αρκετά μικρός και πιθανότατα να συγκλίνει ο αλγόριθμος σε κάποιο τοπικό ελάχιστο.