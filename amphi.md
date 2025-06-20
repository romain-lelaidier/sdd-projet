# Projet : classification

Apprentissage supervisé : $(X,y)\in \R^{(n\times p)} \times \cal Y$ où $\cal Y$ est un ensemble discret
- classification multiclasse : $\cal{Y}=\{1,2,...,C\}$
- classification binaire : $\cal Y=\{0,1\}$ ou $\cal Y=\{-1,1\}$.

On peut utiliser la classification binaire pour le multiclasse avec la méthode 1-vs-reste utilisant $C$ classifieurs binaires pour la classe $c\in \cal Y$ (il faut combiner les réponses avec les probabilités).

Certains algorithmes permettent de faire directement du multiclasse.

## Classification binaire
Modèle $f:\R^p\rightarrow \cal Y=\{0,1\}$ \
Fonction de décision $\varphi:\R^p\rightarrow\R$ telle que $$ f(x)=\begin{cases}0 \text{ si } \varphi(x)\leq\theta\\1\text{ sinon}\end{cases} $$
où $\theta$ est un seuil\
Souvent, $\varphi$ est la probabilité d'appartenir à la classe $\overline 1$ (positive).

### Minimisation du risque empirique
$$ f^\star\in\argmin_{f \in \cal F} \frac{1}{n}\sum_{i=1}^n L(f(x^i), y^i) $$
avec $\cal F$ l'espace des hypothèses et $L$ la fonction de ??? (cf. PC6)

### Evaluation d'un classifieur
1. **Nombre d'erreurs**. Limites :
    - les erreurs dans un certain sens peuvent être plus gênantes que dans l'autre (test de grossesse, test du papillomavirus par frottis)
    - si les classes sont déséquilibrées : $99.99\%\in\overline0$

Matrice de confusion :\
TN = True Negative\
FP = False Positive

<div style="width: 100%; display:flex; justify-content:center">
<table style="width: 70%"><thead>
  <tr>
    <th></th>
    <th colspan="3" style="text-align: center">Prédit</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="3" style="text-align: right; font-weight: bold">Réel</td>
    <td></td>
    <td>0</td>
    <td>1</td>
  </tr>
  <tr>
    <td>0</td>
    <td style="background: #afa">TN</td>
    <td style="background: #faa">FP</td>
  </tr>
  <tr>
    <td>1</td>
    <td style="background: #faa">FN</td>
    <td style="background: #afa">TP</td>
  </tr>
</tbody>
</table>
</div>