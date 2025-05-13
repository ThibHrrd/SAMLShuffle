# SAMLShuffle

**Fuzzer d’assertions SAML pour tester les implementations XML/SAML**

SAMLShuffle est un framework de fuzzing spécialisé dans les assertions SAML. Il génère automatiquement des variations d’une assertion valide (signature wrapping, duplication de nœuds, permutation d’éléments, altération d’IDs et de conditions), recanonicalise et re-signe chaque payload, puis envoie les requêtes à la cible via CLI ou plugin Burp/ZAP. Les réponses sont classifiées (erreur XML, échec de signature, validation incorrecte) et un rapport détaillé des tests est généré.

---

## 🚀 Fonctionnalités

- **Transformations ciblées**  
  - Signature wrapping  
  - Duplication et renommage de nœuds  
  - Réordonnancement d’éléments (Subject, Conditions, AuthnStatement…)  
  - Altération d’`ID`, `InResponseTo`, `NotBefore`/`NotOnOrAfter`
- **Automatisation complète**  
  - DSL YAML/JSON pour définir facilement de nouvelles règles  
  - Recopie, canonicalisation C14n et re-signature via `xmlsec`  
  - Envoi des payloads en CLI ou plugin Burp/ZAP (à voir)
- **Contrôle de la combinatoire**  
  - Priorisation des règles critiques  
  - Limitation de la profondeur de fuzzing  
  - Filtrage des cas invalides à l’avance
- **Reporting et analyse**  
  - Classification automatique des réponses  
  - Génération de rapports détaillés au format JSON/HTML  

---

## 🔧 Installation

```bash
git clone https://github.com/ThibHrrd/SAMLShuffle.git
cd SAMLShuffle
pip install -r requirements.txt
```
