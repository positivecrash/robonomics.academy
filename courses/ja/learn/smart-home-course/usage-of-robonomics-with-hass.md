---
title: "第7課、Home AssistantとRobonomicsの使用方法"
lastUpdate: Thu May 18 2023 10:46:29 GMT+0400 (Samara Standard Time)
description: ホームアシスタントコース
lessonNumber: 8
metaOptions: [RobonomicsとHome Assistantを使用した主権スマートホームを学ぶ]
defaultName: Sovereign Smart Home with Robonomics and Home Assistant
---

## これは何についてですか

このレッスンでは、主要なRobonomics IoTサービスを使用してみます。最初のサービスは、スマートホームデバイスのテレメトリをクエリでき、Home Assistantからデータをリモートで受信できます。2番目のサービスは、Home Assistantの構成のバックアップを生成し、必要に応じて復元します（たとえば、SDカードの障害が発生した場合）。


## パラチェーン機能について

次に、Robonomicsパラチェーンの機能がどのように使用され、Home Assistantユーザーに必要なサービスが提供されるかを見ていきます。 

テレメトリの取得は、すでに知っている<code>datalog</code>パレットに基づいています。一定の期間（ただし、蓄積された重みが許可する限り）ごとに、<code>SUB_CONTROLLER</code>アドレスから<code>datalog.record()</code>トランザクションがパラチェーンに送信され、暗号化されたファイルのIPFSハッシュが含まれています。ここには、IoTデバイスのすべてのデータが収集されています。実際には、テレメトリを取得するためにIoTサブスクリプションに関連するパラチェーンから必要なデータログをリクエストし、それらをキーで復号化します。

バックアップを作成するには、別のRobonomicsパレットである<code>digitalTwin</code>が使用されます。これは、実際の機器のデジタルツイン、つまり技術的特性と履歴データをコピーするアイデアの実装です。まず、<code>digitalTwin.create()</code> extrinsicを使用して、Home Assistantのデジタルツイン用の一意のIDが作成されます。次に、<code>digitalTwin.setSource()</code> extrinsicを使用して、このIDがいくつかのデータ（<code>topic</code>フィールド）とパラチェーン内のアドレス（<code>source</code>フィールド）と結び付けられます。Home Assistantのバックアップでは、バックアップファイルのハッシュが<code>topic</code>に格納され、<code>SUB_OWNER</code>アドレスが<code>source</code>に格納されます。

## 手順

<List type="numbers">

<li>

テレメトリの取得

<List>


<li>

Dappに移動し、[スマートホームテレメトリ](https://dapp.robonomics.network/#/smarthome-telemetry)サービスを選択します。

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/Qmao9RoWcKo2qs4PAGtm5gqHzyAHJcpDqNLgciU35FJeVm', type:'mp4'}]" />

</li>

<li>

<code>CONTROLLER</code>フィールドに<code>SUB_CONTROLLER</code>アドレスを入力します。データを暗号化するためシードフレーズを挿入します。

</li>

<li>

<code>Get telemetry</code>ブロックで、ドロップダウンリストからタイムスタンプを選択し、<code>DOWNLOAD TELEMETRY</code>ボタンを押します。


テレメトリのダウンロードには時間がかかる場合があります。完了後、センサーからの情報が表示されます。

</li>
</List>
</li>


<li>

バックアップの作成

<List>

<li>

バックアップを作成するには、構成ファイルを含む安全なアーカイブを生成するサービスを呼び出します。このサービスはその後、アーカイブをIPFSに追加し、結果のCIDをRobonomics Digital Twinに保存します。

<robo-academy-note type="warning" title="WARNING">
構成を復元するには、Pinata（pinata.cloud）やCrust Network（crust.network）などのカスタムIPFSゲートウェイを使用する必要があります。これがないと、バックアップはローカルIPFSノードにのみ保存され、ローカルノードの障害が発生した場合にHome Assistantの構成を復元できなくなる可能性があります。 
</robo-academy-note>

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/QmVo91dLaAYgFDM1vrL2PYfAffM6SGGC59ZERbfHR44tqW', type:'mp4'}]" />

</li>

<li>

ホームアシスタントのWebインターフェースで、<code>Developer Tools</code> -> <code>Services</code>に移動します。 <code>Robonomics: Save Backup to Robonomics</code>を検索して<code>CALL SERVICE</code>を押します。

</li>

<li>

<code>Notification</code>に表示される<code>Backup was updated in Robonomics</code>の通知が表示されるまで待ちます。

</li>

<li>

構成を復元するには、以前に作成したシードを使用してRobonomics Home Assistant統合を備えた新しいHome Assistantインスタンスをインストールする必要があります（およびすべての前の手順を繰り返す）。また、同じユーザー名とパスワードを使用してMQTTブローカーを設定する必要があります。

<robo-academy-note type="warning" title="WARNING">
Wi-FiまたはMQTT経由でホームアシスタントに接続されている一部のデバイスは、Raspberry PiのローカルIPアドレスを明示的に指定する必要があるため、バックアップを復元すると、このIPが変更されたため利用できない場合があります。これらのデバイスの設定で新しいIPアドレスを再入力する必要があります。これを回避するために、ルーター設定でRaspberry Piの静的ローカルIPを設定できます（この機能をサポートしている場合）。
</robo-academy-note>

<LessonVideo  :videos="[{src: 'https://crustipfs.info/ipfs/QmWmnmkXUcPXsAnQzwN3UEuki2GMYnQDx3vhgjEypCU8aR', type:'mp4'}]" />


</li>

<li>

ホームアシスタントのWebインターフェースで、<code>Developer Tools</code> -> <code>Services</code>に移動します。 <code>Robonomics: Restore from the Backup in Robonomics</code>を検索して<code>CALL SERVICE</code>を押します。 <code>Overview</code>ページに移動して、バックアップのステータスを確認します。

</li>

<li>

ホームアシスタントが再起動を完了すると、構成が復元されます。ステータスが<code>restored</code>に変わった場合でも、ホームアシスタントが自動的に再起動しない場合は、<code>Settings</code> > <code>System</code>に移動し、右上隅の<code>RESTART</code>ボタンをクリックして手動で再起動する必要があります。

</li>

</List>
</li>

</List>

## コースの完了

<List>

<li class="flex"> 

おめでとうございます！主権を持つスマートホームの完全なセットアップと展開を成功裏に完了しました。 Discordチャンネルを訪れて、当社からコース完了証明書をリクエストできます。 [robonomics-academy](https://discord.com/channels/803947358492557312/803947358492557315) チャットで私たちに連絡していただければ、担当者がご連絡いたします。
</li>

<li class="flex">

コース完了の証明は、[Polkadot explorer](https://robonomics.subscan.io/)で検証できる対応するトランザクションです。これらは、サブスクリプションの購入、デバイスのサブスクリプションへの追加、およびデバイスからのデータログの送信に関するトランザクションです。

</li>

</List>