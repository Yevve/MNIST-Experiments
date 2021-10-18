
# a.Går det snabbare att träna nätverken (i antalet epoker) om vi ökar inlärningshastigheten (lr) på nätverken. Kan vi ha en för stor inlärningshastighet och vad händer då?
    Högre inlärnings hastighet ökar epoch accuracy, men för hög inlärnings hastighet gör så att accuracy minskar och inlärnings processen blir ostabil (för lr=1 så ser man hur grafen för validation(ljusblå) blir volatil). Man måste hitta en equlibrium mellan hög och låg hastighet. Se graferna nedan.
![bild 0.01 och 0.2](fig/0.01_and_0.2.svg "0.01 = blå/orange  0.2 = rosa/ljusblå")

![bild 0.4 och 1](fig/0.4_and_1.svg "0.4 = grå/orange  1 = röd/blå")

# b.Vad händer om vi minskar storleken på våra träningsbatcher (batch_size)?Hur ändras prestandardenoch träningstiden.
    En batch size är antalet träningsexempel i en iteration.Ju mer batch size ju mer minne behövs, därav ger minskad batch_size helt enkelt i en långsammare träningstid.

# c.Hur skiljer de båda modellerna sig när det kommer till träningstid? Förklara lite kort om varförde skiljer sig åt.
    CNN, convolutional model är mycket långsammare än non convolutional. CNN uppnår dock en högre accuracy.
    En convolutional-neural-network är en subklass av neural-network som har åtminstone minst ett convolutional layer. Används exempelvis inom lokal information som t.ex pixlar som omgiver en pixel i en bild och minskar även komplexiteten i modellen.
    I exemplet ovan skulle en non conventional å andra sidan gå igen alla pixlar.

![körtid](fig/körtid.svg)

# d.Hur skiljer sig resultatet mellan de olika testseten och varför kan vi se/inte se en skillnad?Är det samma skillnader för båda närverken?
    Som man ser på resultaten så har convolutional ett mycket strörre move data accuracy än non convolutional. När man kollar på resterande resulat så är inte skillnaded lika stora.

    Convolutional:
        Moved Data:     21.34
        Rotated Data:   85.33
        Test Data:      97.93
        Train Data:     99.04
        
    Non Convolutional:
        Moved Data:     15.09
        Rotated Data:   82.47
        Test Data:      96.63
        Train Data:     99.29

# e.Vad händer om vi ökar antalet neuroner. Får vi ett bättre eller sämre resultat. Finns det någon undre eller övre gräns för vad som är bäst?
    För testet användes neuron värdena 32,64,128,256,512,1024 i non_convolutional_model.
    När man ökar antalet neuron så ökar accuracy men det kräver mer kraft/tid för att utföra beräkningar. Som vi ser på graferna så ökar epoch_accuracy för varje ökning av neuron antalet. Vi kan också se att vid 1024 och 512 antal neuroner så är ökningen minimal men det tar nästan dubbelt så lång tid per epoch (5ms för 512, 10ms 1024).
    Den övre gränsen blir då 512 neuroner och den undre gränsen blir 128 neuroner enligt graferna.
![Train](fig/neuronTrain.svg "Neuron Train graph")
![Validation](fig/neuronValidation.svg "Neuron Validation graph")

# f.Öka området som analyseras åt gången medvårt ”convolutional neural network” (detta görs genom att öka värdet på vår kernel_size) och öka även storleken på stegen mellan varje yta som analyseras ” (detta görs genom att öka värdet på strides). Hur stora värden går det att ha på dessa parametrar innan prestandan börjar att sjunka. Vilka var de bästa värdena som du observerade?
    Första testet som kördes var kernel_size (8,8) och strides (1,1). Resultatet i rotated data blev 88.3
    Första testet som kördes var kernel_size (16,16) och strides (2,2) och resultatet på roterad data blev lite sämre(från 88.37 -> 86.26)
    Andra testet som kördes var kernel_size(24,24) och strides (4,4) och resultatet blev ännu sämre: 75.2.

    I bilden är den gråa kernel_size(8,8) och strides (1,1). Som visas syns det att resten av ökningarna ger sämre accuracy.
![kernel](fig/kernel.svg)

# g.Lägg till fler lager och testa om det blir bättre med djupare nätverk. Hur påverkas precisionen och träningstiden?




# Här är mina resultat hittils:

I den här filen ska ni beskriva:
- Era experiment
- Era slutsatser

## Glöm inte!

Glöm inte att ha med figurer:

