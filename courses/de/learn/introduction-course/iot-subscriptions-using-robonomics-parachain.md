---
title: "Lektion #5, IoT-Abonnements mit Robonomics Parachain"
lastUpdate: Thu May 04 2023 12:52:20 GMT+0400 (Samara Standard Time)
description: Sie werden lernen wie Sie ein IoT-Abonnement auf Robonomics Parachain mit echten Token aus unserem Netzwerk kaufen.
lessonNumber: 5
metaOptions: [Online Kurse, Einführungskurs]
defaultName:  Introduction to the ideas of Robonomics
---

Die letzte Lektion unseres Einführungskurses ist höchstwahrscheinlich die anspruchsvollste, denn sie wird Ihnen einiges an Geschick und Geduld abverlangen. Sie werden lernen wie Sie ein IoT-Abonnement auf Robonomics Parachain mit echten Token aus unserem Netzwerk kaufen.


## Einführung

Ein IoT-Abonnement ist ein Zugangsschlüssel zu allen Funktionen die mit der Änderung des Zustands des digital Twins eines cyber-physischen Systems und der Speicherung von Infodermationen über dieses System unter Verwendung des Polkadot/Kusama-Ökosystems verbunden sind. Durch den Besitz eines Abonnements wird der Nutzer von der Gebühr befreit um für die Transaktion zu zahlen. Stattdessen kann der Nutzer einmal in einem bestimmten Zeitraum eine kostenlose Transaktion senden.

Um ein Abonnement zu kaufen ist die Teilnahme an der Abonnement-Auktion erfoderderlich. Daher sollten Sie in dieser Lektion XRT-Tokens erhalten um Gebote abzugeben und Transaktionen durchzuführen. Weitere Infodermationen über diesen Prozess finden Sie auch in [unserem Wiki](https://wiki.robonomics.network/docs/get-subscription).


## Anleitung

<List type="numbers">

<li>

You need around 2 XRT Robonomics Parachain tokens ([über den Token](https://robonomics.network/xrt/)). Wenn Sie diese nicht haben gibt es mehrere Möglichkeiten sie zu erhalten:

a) Wenn Sie beide Tests nach Lektion 2 und Lektion 4 mit 90% korrekten Antworten bestehen, können Sie kostenlose Token für die Lektion anfordern. Überprüfen Sie Ihre Punktzahlen auf [der speziellen Überprüfungs-Dapp](https://lk.robonomics.academy/). Sie müssen speziell 15 von 17 für Lektion 2 und 10 von 11 für Lektion 4 erreichen, und Sie haben zwei Versuche, dies zu tun. Um Token zu erhalten, wenden Sie sich an den Academy-Administrator auf unserem [Discord](https://discord.gg/xqDgG3EGm9) (IBerman#5862).

b) Kaufen XRT-Token an einer der Börsen (check out the [list of exchanges](https://www.coingecko.com/en/coins/robonomics-network#markets/)). Seien Sie vorsichtig wenn Sie nicht mit Kryptowährungsbörsen vertraut sind und denken Sie daran, dass alle Käufe auf Kryptowährungsbörsen potenzielle Risiken bergen können. Kaufen Sie nur die erforderliche Menge an Token um diese Lektion zu absolvieren. Also, keep in mind that Robonomics exists on two networks, Ethereum and Kusama, so each network has its own XRT token. You need a token that used by parachain in Kusama network.

c) Wenn Sie XRT-Token im Ethereum-Netzwerk (im ERC-20-Format) haben, verwenden Sie den [Exodus](https://old.dapp.robonomics.network/#/exodus)-Prozess, um Token vom Ethereum-Netzwerk auf Kusama zu übertragen. Beachten Sie, dass die Übertragung von Token einmal pro Woche erfolgt.

</li>

<li>

IoT-Abonnements werden in einem regulären Auktionsverfahren erworben bei dem der Höchstbietende ein Abonnement erhält.

Bevor Sie versuchen an der Auktion teilzunehmen, sollten Sie prüfen ob es noch freie Plätze gibt. Robonomics [Polkadot/Substratportal](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkusama.rpc.robonomics.network%2F#/chainstate) öffnen mit Chain state Menü. Wählen Sie <code>rws</code> Abfrage mit <code>auctionQueue()</code> und drücken Sie eine '+'-Taste. Sie sollten die IDs der verfügbaren Auktionen sehen; merken Sie sich die ID einer dieser Auktionen. Wenn keine Auktionen angezeigt werden oder verfügbar sind, kontaktieren Sie uns bitte auf unserem Discord in "[🎓robonomics-academy](https://discord.com/channels/803947358492557312/803947358492557315)" channel.

Wählen Sie nun im gleichen Chain state menu <code>rws</code> mit <code>auction(u32): Option&lt;PalletRobonomicsRwsAuctionLedger&gt;</code> und in <code>u32</code> Felder geben Sie die gespeicherte ID der Auktion ein. Nachdem Sie auf die Schaltfläche "+" geklickt haben, werden Ihnen Informationen über eine interessante Auktion angezeigt. Wenn die <code>winner</code> Feld hat <code>null</code> Wert, dann hat niemand dieses Abonnement und Sie können versuchen es zu bekommen.

</li>

<li>

Jetzt können Sie mit Ihren XRT-Tokens ein Gebot abgeben. 

Gehen Sie zum Menü Entwickler -> Extrinsic und wählen Sie für dasselbe polkadot.js-Konto das Sie in der vorherigen Lektion extrinsic verwendet haben <code>rws</code> mit <code>bid(index, amount)</code>. Im <code>index</code> geben Sie die ID der gewünschten Auktion ein. Im <code>amount</code> Feld sollten Sie die Anzahl der Token für das Gebot eingeben, umgerechnet in "Wiener" (1 XRT = 1 000 000 000 Wn). Bitte prüfen Sie den aktuellen Abonnementpreis in unserer [Dapp](https://dapp.robonomics.network/#/subscription). 

Senden Sie die Transaktion ab und wenn Sie Glück haben erhalten Sie das IoT-Abonnement. Sie können überprüfen, ob Ihre Polkadot-Adresse das Abonnement besitzt indem Sie das gleiche Chain state menu aufrufen.

</li>

<li>

Der letzte Schritt besteht darin, Geräte für Ihr IoT-Abonnement hinzuzufügen. 

Das bedeutet einfach, dass Sie Ihrem Abonnement zusätzliche Polkadot-Adressen zuweisen die Sie oder Ihre Geräte verwenden können um Extrinsics auszuführen (zum Beispiel um Geräte zu starten oder Gerätedaten an die Blockchain zu senden). 


Bevor Sie beginnen, erstellen Sie ein neues Konto für Robonomics Parachain (Anleitung in [unserem Wiki](https://wiki.robonomics.network/docs/create-account-in-dapp/)), und nennen es der Einfachheit halber "smart device".

Gehen Sie dann zum Menü Entwickler -> Extrinsic, und wählen Sie <code> rws</code> mit <code>setDevices()</code>. Verwenden Sie in der Geräteliste die Schaltfläche "Add item", um Geräte hinzuzufügen, und wählen Sie ein kürzlich erstelltes Konto für intelligente Geräte aus. Danach übermitteln Sie die Transaktion.

Die Geräteadresse sollte zum Abonnement hinzugefügt werden. Sie können sie im Chain state menu durch Abfrage überprüfen <code>rws</code> mit <code>devices()</code> für Ihr polkadot.js-Konto, das das Abonnement hat.

</li>

</List>

<Result>

Die Lektion wird als abgeschlossen betrachtet, wenn der Kauf eines IoT-Abonnements und das Hinzufügen eines Geräts erfolgreich abgeschlossen wurde.

Sie können Ihre Ergebnisse auf [der speziellen Überprüfungs-Dapp](https://lk.robonomics.academy/) überprüfen. Zur Autorisierung in der Überprüfungs-Dapp verwenden Sie dasselbe Konto in Polkadot.js, das während des Kurses verwendet wurde.

</Result>