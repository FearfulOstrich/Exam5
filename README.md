# Ex1
- Create a class `Warlock` ( Warlock.hpp + Warlock.cpp )
  - Compile avec `c++ --flags main.cpp Warlock.cpp` donc `#include "Warlock.hpp"` dans le .cpp !!
- Suivre la norme de coplien
- Pas constructible par copie ni copiable
  - Prototyper les fonctions mais ne pas les definir.

# Ex2
- Creer 2 classes abstraites `ASpell` et `ATarget`.
  - Pas copiable ni constructible par copie.
  - Comporte une fonction membre virtuelle pure `clone`.
- Creer une class `Shwooff` qui herite de `ASpell`.
  - 2 attributs `name` et `effects`.
  - une fonction `use` qui prend une `const ATarget&` en argument.
- Creer une class `Dummy` qui herite de `ATarget`.
  - 1 attribut `type`.
- Ajouter au Warlock les fonctions:
  - learnSpell( ASpell* );
  - forgetSpell( std::string name );
  - useSpell( std::string name, ATarget& target ); 
  - Le Warlock ne peut pas apprendre plus d'une fois le meme Spell.
  - Utiliser un vector pour stocker les differents `ASpell*`

# Ex3
- Ajouter 2 nouveaux Spell.
- Ajouter 1 nouveau Target.
- Ajouter une classe `SpellBook`.
  - Le SpellBook peut:
    - learnSpell( ASpell* );
    - forgetSpell( std::string name );
    - ASpell* createSpell( std::string name );
  - Le SpellBook ne peut contenir 2 fois le meme Spell (vector -> iterateurs pour verifier )
- Le Warlock aura un SpellBook en attribut.
- Les fonctions `learnSpell` et `forgetSpell` appellent celles du Spellbook.
- La fonction `useSpell` cree un Spell du SpellBook puis l'utilise sur la Target !
