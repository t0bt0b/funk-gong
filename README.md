# KSN Projects
School project by Prestros Fabian, Rath Tobias and Rucker Josef


## FUNKGONG

![FUNKGONG Flow-Graph](Images/FUNKGONG.png)

### Aufbau

- **UHD USRP Source:** Dieser Block ist die Quelle des Signals, normalerweise verbunden mit einem USRP (Universal Software Radio Peripheral) Gerät (ETTUS B200). Es ist konfiguriert, um ein Signal mit einer bestimmten Sample-Rate (10 Msps - Mega Samples per Second), einer Zentralfrequenz (434 MHz), und Bandbreite (10 MHz) zu erfassen. AGC (Automatic Gain Control) ist aktiviert, um die Signalstärke automatisch anzupassen.

- **QT GUI Range:** Dieser Block ist eine Benutzeroberfläche, die es dem Benutzer ermöglicht, einen Parameter, in diesem Fall die Frequenz, interaktiv anzupassen. Die Einstellungen erlauben eine Anpassung von 430 MHz bis 440 MHz in 1 MHz Schritten.

- **Rational Resampler:** Dieser Block ändert die Sampling-Rate des Signals durch Interpolation und Dezimierung, in diesem Fall wird das Signal durch 25 dezimiert, um die Anzahl der Samples pro Sekunde zu reduzieren, ohne die Information des Signals zu verändern.

- **Low Pass Filter:** Ein Tiefpassfilter, der Frequenzen über einer bestimmten Grenze abschneidet. Dieser ist hier eingestellt, um Frequenzen über 100 kHz abzuschneiden und benutzt ein Hamming-Fenster für die Filtergestaltung.

- **AM Demod:** Dieser Block demoduliert ein AM (Amplitudenmoduliertes) Signal. Es verwendet die vorher definierten Raten für das Audiosignal, um es auf eine hörbare Form zu bringen.

- **Rational Resampler (nach dem AM Demod):** Ein weiterer Resampling-Block, der das demodulierte Audiosignal auf eine niedrigere Sample-Rate (48 kHz) bringt, passend für die Audioausgabe.

- **Audio Sink:** Dieser Block gibt das verarbeitete Audiosignal an den Audioausgang des Computers zur akustischen Wiedergabe aus.

- **Wav File Sink:** Parallel dazu wird das Audiosignal auch in eine WAV-Datei (**gong.wav**) geschrieben. Es wird mit einer Sample-Rate von 48 kHz und einer Auflösung von 16 Bit pro Sample gespeichert.

- **QT GUI Frequency Sink und QT GUI Waterfall Sink:** Diese beiden Blöcke bieten eine visuelle Darstellung des verarbeiteten Signals. Der Frequency Sink zeigt ein Spektrum (FFT-Größe 1024) des Signals, während der Waterfall Sink eine Wasserfalldarstellung über die Zeit bietet. Beide nutzen die gleiche Zentralfrequenz und Bandbreite wie der USRP-Quellblock.

- **Variable:** Es gibt zwei Variable-Blöcke (**audio_samp_rate** und **decimation_rf**), die zur Konfiguration anderer Blöcke genutzt werden. Sie sind globale Parameter, die in mehreren Blöcken verwendet werden können.


## funkR

![funkR Flow-Graph](Images/funkR.png)

### Funktion?


## gong-tx

![gong-tx Flow-Graph](Images/gong-tx.png)

### Funktion?
