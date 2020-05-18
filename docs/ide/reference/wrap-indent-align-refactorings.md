---
title: ラップ、インデント、およびリファクタリングの整理
description: メソッド呼び出しのチェーンをラップし、配置する方法について説明します。
ms.date: 03/10/2020
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: d801f052cb02e6a5b53189eeae342b9015d30f9b
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79093878"
---
# <a name="wrap-indent-and-align-refactorings"></a>ラップ、インデント、およびリファクタリングの整理

## <a name="wrap-and-align-call-chains"></a>呼び出しチェーンのラップおよび配置

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** メソッド呼び出しのチェーンをラップし、配置できます。

**条件:** 1 つのステートメントにある複数のメソッド呼び出しで構成される長いチェーンがあること。

**理由:** ユーザー設定に従ってラップまたはインデントされていると、長い一覧に目を通すときに便利です。

### <a name="how-to"></a>方法

1. 任意の呼び出しチェーンにカーソルを置きます。
2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
3. **[呼び出しチェーンのラップ]** または **[呼び出しチェーンのラップおよび配置]** を選択し、リファクタリングを受け入れます。

   ![呼び出しチェーンのラップおよび配置](media/wrap-call-chain.png)

## <a name="wrap-indent-and-align-parameters-or-arguments"></a>ラップ、インデント、およびパラメーターまたは引数の整列

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** ラップ、インデント、およびパラメーターまたは引数の整列を行えます。

**条件:** 複数のパラメーターまたは引数があるメソッド宣言または呼び出しがある場合です。

**理由:** ユーザー設定に従ってラップまたはインデントされていると、パラメーターまたは引数の長い一覧に目を通すときに便利です。

### <a name="how-to"></a>方法

1. パラメーター一覧にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![ラップ、インデント、およびパラメーターの整列](media/wrap-parameters.png)

3. **[すべてのパラメーターを折り返します]** を選択して、リファクタリングを受け入れます。

## <a name="wrap-binary-expressions"></a>二項式のラップ

このリファクタリングは以下に適用されます。

- C#

- Visual Basic

**概要:** 二項式をラップすることができます。

**条件:** 二項式があること。

**理由:** 二項式はユーザー設定に従ってラップされていると読み取りやすくなります。

### <a name="how-to"></a>方法

1. 二項式にカーソルを置きます。
2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
3. **[式を折り返す]** を選択して、リファクタリングを受け入れます。

   ![呼び出しチェーンのラップおよび配置](media/wrap-binary-expression.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)