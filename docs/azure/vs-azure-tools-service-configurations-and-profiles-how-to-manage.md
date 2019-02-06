---
title: サービス構成とプロファイルを管理する方法 | Microsoft Docs
description: サービス構成とプロファイルの構成ファイルを使用する方法について説明します。構成ファイルには、デプロイ環境の設定とクラウド サービスの発行設定が保存されます。
author: ghogen
manager: jillfra
assetId: 7da8c551-fb06-4057-b5c7-c77f4b39d803
ms.prod: visual-studio-dev15
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/11/2017
ms.author: ghogen
ms.openlocfilehash: 4c4f359051ba98c75778ccc0d8c8b653558097a3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2019
ms.locfileid: "55140653"
---
# <a name="how-to-manage-service-configurations-and-profiles"></a>サービス構成とプロファイルを管理する方法
## <a name="overview"></a>概要
クラウド サービスを発行すると、Visual Studio は、サービス構成とプロファイルという 2 種類の構成ファイルに構成情報を保存します。 サービス構成 (.cscfg ファイル) には、Azure クラウド サービスのデプロイ環境の設定が保存されます。 Azure は、クラウド サービスを管理するときに、これらの構成ファイルを使用します。 その一方で、プロファイル (.azurePubxml ファイル) には、クラウド サービスの発行設定が保存されます。 この設定は、発行ウィザードで選択された内容の記録であり、Visual Studio によってローカルで使用されます。 ここでは、両方の種類の構成ファイルを使用する方法について説明します。

## <a name="service-configurations"></a>サービス構成
複数のサービス構成を作成し、それらを各デプロイ環境に使用できます。 たとえば、ローカル環境用のサービス構成を作成して Azure アプリケーションの実行とテストに使用し、別のサービス構成を運用環境用に作成します。

これらのサービス構成は、要件に基づいて追加、削除、名前変更、および変更できます。 次の図に示すように、Visual Studio からこれらのサービス構成を管理できます。

![[サービス構成の管理]](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/manage-service-config.png)

ロールのプロパティ ページから **[構成の管理]** ダイアログ ボックスを開くこともできます。 Azure プロジェクトのロールのプロパティを開くには、ロールのショートカット メニューを開き、 **[プロパティ]** をクリックします。 **[設定]** タブで、**[サービス構成]** ボックスの一覧を展開し、**[管理]** を選択して **[構成の管理]** ダイアログ ボックスを開きます。

### <a name="to-add-a-service-configuration"></a>サービス構成を追加するには
1. ソリューション エクスプローラーで、Azure プロジェクトのショートカット メニューを開き、 **[構成の管理]** を選択します。

    **[サービス構成の管理]** ダイアログ ボックスが表示されます。
2. サービス構成を追加するには、既存の構成のコピーを作成する必要があります。 これを行うには、[名前] ボックスの一覧で、コピーする構成を選択し、 **[コピーの作成]** を選択します。
3. (省略可能) サービス構成の名前を変更するには、[名前] ボックスの一覧から新しいサービス構成を選択し、 **[名前の変更]** を選択します。 **[名前]** ボックスに、このサービス構成に使用する名前を入力し、**[OK]** を選択します。

    ServiceConfiguration.[New Name].cscfg という新しいサービス構成ファイルがソリューション エクスプローラーの Azure プロジェクトに追加されます。

### <a name="to-delete-a-service-configuration"></a>サービス構成を削除するには
1. ソリューション エクスプローラーで、Azure プロジェクトのショートカット メニューを開き、 **[構成の管理]** を選択します。

    **[サービス構成の管理]** ダイアログ ボックスが表示されます。
2. サービス構成を削除するには、**[名前]** ボックスの一覧から削除する構成を選択し、**[削除]** を選択します。 この構成を削除することを確認するダイアログ ボックスが表示されます。
3. **[削除]** を選択します。

     ソリューション エクスプローラーの Azure プロジェクトからサービス構成ファイルが削除されます。

### <a name="to-rename-a-service-configuration"></a>サービス構成の名前を変更するには
1. ソリューション エクスプローラーで、Azure プロジェクトのショートカット メニューを開き、 **[構成の管理]** を選択します。

    **[サービス構成の管理]** ダイアログ ボックスが表示されます。
2. サービス構成の名前を変更するには、**[名前]** ボックスの一覧から新しいサービス構成を選択し、**[名前の変更]** を選択します。 **[名前]** ボックスに、このサービス構成に使用する名前を入力し、**[OK]** を選択します。

    ソリューション エクスプローラーの Azure プロジェクトでサービス構成ファイルの名前が変更されます。

### <a name="to-change-a-service-configuration"></a>サービス構成を変更するには
* サービス構成を変更する場合は、Azure プロジェクトで変更するロールのショートカット メニューを開き、 **[プロパティ]** を選択します。 「[方法:Visual Studio を使用した Azure クラウド サービスのロールの構成](vs-azure-tools-configure-roles-for-cloud-service.md)」を参照してください。

## <a name="make-different-setting-combinations-by-using-profiles"></a>プロファイルを使用してさまざまな設定を組み合わせる
プロファイルを使用すると、目的に応じて異なる設定の組み合わせを自動的に**発行ウィザード**に入力できます。 たとえば、デバッグ用にプロファイルを 1 つ作成し、リリース ビルド用に別のプロファイルを作成します。 その場合、**デバッグ** プロファイルでは **IntelliTrace** が有効になり、**デバッグ**構成が選択されます。**リリース** プロフィールでは **IntelliTrace** が無効になり、**リリース**構成が選択されます。 また、別のプロファイルを使用して、別のストレージ アカウントでサービスをデプロイすることもできます。

初めてウィザードを実行すると、既定のプロファイルが作成されます。 プロファイルが格納されたファイルは、.azurePubXml 拡張子が付き、Azure プロジェクトの **Profiles** フォルダーの下に追加されます。 後でウィザードを実行するときに手動で別の選択を指定すると、ファイルは自動的に更新されます。 次の手順を実行する前に、クラウド サービスを少なくとも 1 回発行する必要があります。

### <a name="to-add-a-profile"></a>プロファイルを追加するには
1. Azure プロジェクトのショートカット メニューを開き、 **[発行]** を選択します。
2. 次の図に示すように、**[ターゲット プロファイル]** ボックスの横にある **[プロファイルの保存]** ボタンを選択します。 プロファイルが自動的に作成されます。

    ![Create an new profile](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/create-new-profile.png)
3. プロファイルが作成されたら、**[ターゲット プロファイル]** ボックスの一覧の **[<管理>]** を選択します。

    次の図に示すように、 **[プロファイルの管理]** ダイアログ ボックスが表示されます。

    ![Manage Profiles Dialog](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/manage-profiles.png)
4. **[名前]** ボックスの一覧で、プロファイルを選択し、**[コピーの作成]** を選択します。
5. **[閉じる]** をクリックします。

    新しいプロファイルが [ターゲット プロファイル] ボックスの一覧に表示されます。
6. **[ターゲット プロファイル]** ボックスの一覧で、先ほど作成したプロファイルを選択します。 選択したプロファイルで選択されている内容が、発行ウィザードの設定項目に入力されます。
7. **[前へ]** と **[次へ]** を選択して発行ウィザードの各ページを表示し、このプロファイルの設定をカスタマイズします。 詳細については、 [Azure アプリケーションの公開ウィザード](http://go.microsoft.com/fwlink/p/?LinkID=623085) に関するページを参照してください。
8. 設定のカスタマイズが完了したら、 **[次へ]** を選択して [設定] ページに戻ります。 プロファイルが保存されるのは、これらの設定を使用してサービスを発行したときか、プロファイルの一覧の横にある **[保存]** を選択したときです。

### <a name="to-rename-or-delete-a-profile"></a>プロファイルを削除するには
1. Azure プロジェクトのショートカット メニューを開き、 **[発行]** を選択します。
2. **[ターゲット プロファイル]** ボックスの一覧の **[管理]** を選択します。
3. **[プロファイルの管理]** ダイアログ ボックスで、削除するプロファイルを選択し、**[削除]** を選択します。
4. 確認のダイアログ ボックスが表示されたら、 **[OK]** を選択します。
5. **[閉じる]** を選択します。

### <a name="to-change-a-profile"></a>プロファイルを変更するには
1. Azure プロジェクトのショートカット メニューを開き、 **[発行]** を選択します。
2. **[ターゲット プロファイル]** ボックスの一覧で、変更するプロファイルを選択します。
3. **[前へ]** と **[次へ]** を選択して発行ウィザードの各ページを表示し、目的の設定を変更します。 詳細については、 [Azure アプリケーションの公開ウィザード](http://go.microsoft.com/fwlink/p/?LinkID=623085) に関するページを参照してください。
4. 設定の変更が完了したら、**[次へ]** を選択して **[設定]** ページに戻ります。
5. (省略可能) **[発行]** を選択し、新しい設定を使用してクラウド サービスを発行します。 この時点でクラウド サービスを発行せずに発行ウィザードを閉じると、変更をプロファイルに保存するかどうかをたずねるメッセージが表示されます。

## <a name="next-steps"></a>次の手順
Visual Studio で Azure プロジェクトの他の部分を構成する方法については、 [Azure プロジェクトの構成](http://go.microsoft.com/fwlink/p/?LinkID=623075)