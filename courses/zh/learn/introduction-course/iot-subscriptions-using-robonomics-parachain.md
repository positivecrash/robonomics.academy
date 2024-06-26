---
title: "第5课，使用Robonomics Parachain购买IoT订阅"
lastUpdate: Thu May 04 2023 12:53:55 GMT+0400 (Samara Standard Time)
description: 您将学习如何使用我们网络的真实代币在Robonomics Parachain上购买IoT订阅。
lessonNumber: 5
metaOptions: [学习, Robonomics理念介绍]
defaultName:  Introduction to the ideas of Robonomics
---

我们的入门课程的最后一课很可能是最具挑战性的，因为它需要您一些耐心。 您将学习如何使用我们网络的真实代币在 Robonomics 平行链上购买 IoT 订阅。


## 介绍

IoT订阅是访问与改变网络物理系统数字孪生状态和使用Polkadot / Kusama生态系统存储信息相关的所有功能的关键。拥有一个订阅可以使用户免除支付交易费。相反，用户可以在一定时间内发送一次免费交易。

购买订阅的主要方式是参与订阅拍卖，因此在这节课中，您应该获取XRT代币以进行竞标和提交交易。有关此过程的更多信息也可在[我们的wiki](https://wiki.robonomics.netw或k/docs/get-subscription)上找到。

## 说明

<List type="numbers">

<li>

您需要大约2个XRT Robonomics Parachain代币（[关于代币](https://robonomics.netw或k/xrt/)）。如果您没有，您有几个选择：

a) 如果您在第2课和第4课后都以90%的正确答案通过了两次测试，您可以请求免费代币以完成本课程。在[特殊检查dapp](https://lk.robonomics.academy/)检查您的分数。具体来说，您需要在第2课中得到17分中的15分，在第4课中得到11分中的10分，您有两次尝试机会。要获取代币，请在我们的[Discord](https://discord.gg/xqDgG3EGm9)上联系学院管理员（IBerman#5862）。

b) 在交易所之一购买XRT代币（查看[交易所列表](https://www.coingecko.com/en/coins/robonomics-network#markets/)）。如果您不熟悉加密货币交易所，请注意所有加密货币交易所的购买可能存在潜在风险，只购买通过本课程所需的代币数量。另外，请记住Robonomics存在于两个网络，以太坊和Kusama，因此每个网络都有自己的XRT代币。您需要使用Kusama网络中的parachain使用的代币。

c) 如果您在以太坊网络（ERC-20格式）中拥有XRT代币，请使用[Exodus](https://old.dapp.robonomics.network/#/exodus)过程将代币从以太坊网络转移到Kusama。请记住，代币的转移每周进行一次。

</li>

<li>

通过拍卖流程购买IoT订阅，最高出价者获得订阅。

在尝试参与拍卖之前，您应该检查是否有任何可用的拍卖。打开Robonomics [Polkadot/Substrate门户](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkusama.rpc.robonomics.network%2F#/chainstate)，选择Chain state菜单。选择<code>rws</code>查询与<code>auctionQueue()</code>，然后按“+”按钮。您应该看到可用拍卖的ID；记住其中一个ID。如果没有显示或可用拍卖，请在我们的Discord的“[🎓robonomics-academy](https://discord.com/channels/803947358492557312/803947358492557315)”频道联系我们。

现在，在同一Chain state菜单中，选择<code>rws</code>与<code>auction(u32): Option&lt;PalletRobonomicsRwsAuctionLedger&gt;</code>，在32字段中输入记住的拍卖ID。按下“+”按钮后，您将看到有关一个有趣拍卖的信息。如果<code>winner</code>字段的值为<code>null</code>，则没有人拥有此订阅，您可以尝试获取。

</li>

<li>

使用您的XRT代币进行竞标。

转到开发者->外部菜单，并选择与上一课程中使用的相同Polkadot.js帐户的外部<code>rws</code>和<code>bid(index, amount)</code>。在<code>index</code>字段中输入感兴趣的拍卖ID。在<code>amount</code>字段中，您应该输入您的竞标代币数量，转换为“维纳”（1 XRT = 1 000 000 000 Wn）。在我们的[dapp](https://dapp.robonomics.network/#/subscription)中检查当前的最低认购价格。 

提交交易，如果幸运的话，您将获得IoT订阅。您可以通过相同的链状态菜单检查您的Polkadot地址是否拥有订阅。

</li>

<li>

最后一步是为您的IoT订阅添加设备。

这意味着您将额外的Polkadot地址分配给您的订阅，以便它们可以执行外部操作（例如，启动设备或将设备数据发送到区块链）。

首先，为Robonomics Parachain创建一个新帐户（在[我们的wiki](https://wiki.robonomics.network/docs/create-account-in-dapp/)上的指南），并为方便起见将其命名为“智能设备”。

然后，转到开发者->外部菜单，并选择<code>rws</code>和<code>setDevices()</code>。在设备列表中，使用“添加项目”按钮添加设备，并选择最近创建的帐户。之后，提交交易。

设地址应添加到订阅中。您可以通过查询<code>rws</code>和<code>devices()</code>在具有订阅的Polkadot.js帐户的链状态菜单中检查。

</li>

</List>

<Result>

在购买IoT订阅并为其添加一个设备的成功交易后，课程将被视为已完成。交易应出现在您的Polkadot资源管理器中。

您可以在[特殊检查dapp](https://lk.robonomics.academy/)上检查您的结果。在检查dapp上进行授权时，请使用在课程期间使用的Polkadot.js中的相同帐户。

</Result>