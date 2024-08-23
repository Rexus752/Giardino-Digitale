```
#include "contact.h"
#include <strings.h>

/**  Un tipo di dato per i contatti telefonici e cyberspaziali
typedef struct contact {
   char* name;   
   char* surname;
   char* mobile;
   char* url;
} Contact, *ContactPtr;
*/

/**  @brief Controlla se due contatti hanno lo stesso nome e cognome
      @param c1 il primo  contatto 
      @param c2 il secondo contatto
      @return 1 se i due contatti sono uguali, 0 altrimenti
*/
_Bool contactEq(Contact c1, Contact c2) {
    return strcasecmp(c1.name, c2.name) && strcasecmp(c1.surname, c2.surname) ? 1 : 0;
}


/**  @brief Controlla se due contatti hanno lo stesso nome e cognome∗ 
      @param pc1 il puntatore al primo  contatto (non può essere NULL)
      @param pc2 il puntatore al secondo  contatto (non può essere NULL)
      @return 1 se i due contatti sono uguali, 0 altrimenti
*/
_Bool contactEqEff(const Contact const *pc1, const Contact const *pc2) {
    return strcasecmp(pc1->name, pc2->name) && strcasecmp(pc1->surname, pc2->surname) ? 1 : 0;
}


/**  @brief Confronta due contatti per cognome rispetto all'ordine lessicografico e, se il cognome e' lo stesso, per nome
      @param c1 il primo  contatto 
      @param c2 il secondo contatto
      @return -1 se c1 minore di c2, 0 se c1 uguale a c2, 1 se c1 maggiore di c2
*/
int contactCmp(Contact c1, Contact c2) {
    return 0;
}


/**  @brief Confronta due contatti per cognome rispetto all'ordine lessicografico e, se il cognome e' lo stesso, per nome
      @param pc1 il puntatore al primo  contatto (non può essere NULL)
      @param pc2 il puntatore al secondo  contatto (non può essere NULL)
      @return -1 se *pc1 minore di *pc2, 0 se *pc1 uguale a *pc2, 1 se *pc1 maggiore di *pc2
*/
int contactCmpEff(const Contact const *pc1, const Contact const *pc2) {
    // Controllo sui cognomi
    if(pc1->surname != NULL && pc2->surname != NULL) {
        int pc1_surname_length = strlen(pc1->surname);
        int pc2_surname_length = strlen(pc2->surname);
        int min_surname_length = pc1_surname_length < pc2_surname_length ? pc1_surname_length : pc2_surname_length;
        for(int i = 0; i < min_surname_length; i++) {
            int pc1_char = (int)tolower(pc1->surname[i]);
            int pc2_char = (int)tolower(pc2->surname[i]);
            if(pc1_char < pc2_char) return -1;
            else if (pc1_char > pc2_char) return 1;
            return 0;
            
            
        }
        if(pc1_surname_length < pc2_surname_length) return 1;
        else if (pc1_surname_length > pc2_surname_length) return -1;
        return 0;
    }
    
    
    else return 0;
    /*
    // Cognomi uguali, si passa al controllo sui nomi
    int cnt1_name_length = strlen(cnt1->name);
    int cnt2_name_length = strlen(cnt2->name);
    int min_surname_length = cnt1_surname_length < cnt2_surname_length ? cnt1_surname_length : cnt2_surname_length;
    for(int i = 0; i < min_surname_length; i++) {
        int cnt1_char = char_format(cnt1->surname[i]);
        int cnt2_char = char_format(cnt2->surname[i]);
        if(cnt1_char < cnt2_char) return -1;
        else if (cnt1_char > cnt2_char) return 1;
    }
    if(cnt1_surname_length < cnt2_surname_length) return 1;
    else if (cnt1_surname_length > cnt2_surname_length) return -1;
    */
};

```