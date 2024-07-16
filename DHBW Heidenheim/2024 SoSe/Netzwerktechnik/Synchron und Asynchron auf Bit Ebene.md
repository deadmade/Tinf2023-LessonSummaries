## Synchrone Kommunikation

Bei der synchronen Kommunikation werden Datenbits zusammen mit einem Taktsignal übertragen. Das bedeutet, dass sowohl der Sender als auch der Empfänger durch ein gemeinsames Taktsignal synchronisiert sind. Dieses Taktsignal sorgt dafür, dass beide Parteien zur gleichen Zeit "wissen", wann ein neues Bit übertragen wird. Hier sind die Hauptmerkmale der synchronen Kommunikation:

1. **Taktsignal:** Ein separates Taktsignal wird verwendet, um die Synchronisierung zwischen Sender und Empfänger sicherzustellen. Dies kann ein separates Signal sein oder in das Datenstrom eingebettet werden.
2. **Kontinuierliche Übertragung:** Daten können kontinuierlich und ohne Pausen zwischen den Bits übertragen werden.
3. **Effizienz:** Da das Taktsignal eine genaue Synchronisierung ermöglicht, kann die Datenübertragung effizient und schnell sein.

### Beispiel: SPI (Serial Peripheral Interface)

SPI ist ein Beispiel für ein synchrones Kommunikationsprotokoll. Hierbei werden Daten über separate Datenleitungen (MOSI und MISO) und eine Taktsignalleitung (SCLK) übertragen.

## Asynchrone Kommunikation

Bei der asynchronen Kommunikation gibt es kein gemeinsames Taktsignal zwischen dem Sender und dem Empfänger. Stattdessen werden Start- und Stoppbits verwendet, um den Beginn und das Ende eines Datenwortes zu markieren. Hier sind die Hauptmerkmale der asynchronen Kommunikation:

1. **Start- und Stoppbits:** Jedes Datenwort beginnt mit einem Startbit und endet mit einem Stoppbit. Dies ermöglicht es dem Empfänger, den Anfang und das Ende jedes Datenwortes zu erkennen.
2. **Fehlende kontinuierliche Synchronisierung:** Da es kein gemeinsames Taktsignal gibt, sind die Daten nicht kontinuierlich synchronisiert. Der Empfänger muss das Timing der Bits selbstständig erkennen.
3. **Flexibilität:** Asynchrone Kommunikation ist flexibler, da sie keine exakte Synchronisierung zwischen Sender und Empfänger erfordert. Dies kann jedoch zu einer geringeren Effizienz führen.

### Beispiel: UART (Universal Asynchronous Receiver/Transmitter)

UART ist ein Beispiel für ein asynchrones Kommunikationsprotokoll. Hierbei wird jedes Datenbyte mit einem Startbit, dem eigentlichen Datenbits und einem Stoppbit übertragen.

## Vergleich

|Merkmal|Synchrone Kommunikation|Asynchrone Kommunikation|
|---|---|---|
|**Taktsignal**|Ja|Nein|
|**Start- und Stoppbits**|Nein|Ja|
|**Datenübertragungsrate**|Höher|Niedriger|
|**Komplexität der Implementierung**|Höher (wegen Taktsignal)|Niedriger|
|**Kontinuierliche Übertragung**|Ja|Nein|
|**Beispielprotokolle**|SPI, I2C|UART, RS-232|