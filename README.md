# statistics-vs-ai


📘 Logistisk regresjon og nevrale nett

Dette prosjektet forklarer matematikken bak logistisk regresjon og korleis eit eitt-lags nevralt nett i realiteten er den same modellen. Målet er å gjere det enkelt å forstå både samband og skilnader.


🔍 Oversikt
Kva er logistisk regresjon?
Kva gjer sigmoid-funksjonen?
Kva er log-loss?
Kvifor er eitt-lags nevrale nett eigentleg logistisk regresjon?
Kvifor varierer vektene mellom modellane?
Kodeeksempel i både scikit-learn og keras


🧠 Logistisk regresjon – grunnidé
Logistisk regresjon modellerer sannsynet for at ei observasjon høyrer til ein klasse:

p = σ(wᵀx + b)

Der:
x = inputvariablar
w = vekter
b = bias
σ = sigmoid-funksjonen

Dette gir ein sannsynsverdi mellom 0 og 1.

🔢 Sigmoid-funksjonen
Sigmoid gjer ein lineær kombinasjon om til eit sannsyn:
σ(z) = 1 / (1 + e^(–z))

Eigenskapar:
Verdien er alltid mellom 0 og 1

Brukt direkte i logistisk regresjon
Brukt som aktivering i enkle nevrale nett

📉 Tapfunksjon: Log-loss
For å trene modellen brukar vi log-loss:

L = -\[y \* log(p) + (1 − y) \* log(1 − p)]

Dette straffar:
høge sannsyn når modellen tek feil
låge sannsyn når modellen har rett

🤖 Éin-lags nevralt nett = logistisk regresjon
Eit nevralt nett med berre eitt Dense-lag og ein sigmoid i utgangen:

p = σ(Wᵀx + b)
Dette er identisk matematisk formel som i logistisk regresjon.
Forskjellen ligg i optimaliseringsmetoden, ikkje i modellen.

⚙️ Optimalisering: Keras vs. scikit-learn

Modell	Optimisator	Type
scikit-learn LogisticRegression (lbfgs)	LBFGS	2.-ordens metode

Keras Dense + sigmoid	Adam / SGD	1.-ordens gradientmetodar

Poenget:
Modellane har same form, men treningsmetoden gjer at dei kan ende opp med ulike vekter.

❓ Kvifor får LR og NN ulike vekter?
Sjølv om modellane er matematiske tvillingar, kan vektene variere fordi:
Dei startar med ulike initialverdiar
Dei brukar ulike optimisarar
Dei har ulik læringsrate

Adam/SGD kan stoppe i andre minimum enn LBFGS

Men:
👉 Beslutningsgrensa og prediksjonane blir svært like.
