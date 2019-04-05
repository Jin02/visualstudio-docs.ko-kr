---
title: Publish-WebApplicationWebSite(Windows PowerShell 스크립트) | Microsoft Docs
description: Azure 웹 사이트에 웹 프로젝트를 게시하는 방법에 대해 알아봅니다. 없는 경우 이 스크립트는 Azure 구독에 필요한 리소스를 만듭니다.
author: ghogen
manager: jillfra
assetId: 63cfaa2d-f04d-40dc-8677-345385c278d5
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2016
ms.author: ghogen
ms.openlocfilehash: daf3e22176ef950177ebdb22ae6a9e36bcb5dd83
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58981790"
---
# <a name="publish-webapplicationwebsite-windows-powershell-script"></a>Publish-WebApplicationWebSite (Windows PowerShell 스크립트)
## <a name="syntax"></a>구문
Azure 웹 사이트에 웹 프로젝트를 게시합니다. 없는 경우 스크립트는 Azure 구독에 필요한 리소스를 만듭니다.

    Publish-WebApplicationWebSite
    –Configuration <configuration>
    -SubscriptionName <subscriptionName>
    -WebDeployPackage <packageName>
    -DatabaseServerPassword @{Name = "name"; Password = "password"}
    -SendHostMessagesToOutput
    -Verbose


## <a name="configuration"></a>구성
배포의 세부 정보를 설명하는 JSON 구성 파일에 대한 경로입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |true |
| 위치 |named |
| 기본값 |없음 |
| Accept Pipeline Input? |False |
| Accept Wildcard Characters? |False |

## <a name="subscriptionname"></a>SubscriptionName
웹사이트를 만들려는 Azure 구독의 이름입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| Position |named |
| 기본값 |없음 |
| Accept Pipeline Input? |False |
| Accept Wildcard Characters? |False |

## <a name="webdeploypackage"></a>WebDeployPackage
웹 사이트에 게시하는 웹 배포 패키지에 대한 경로입니다. Visual Studio에서 웹 게시 마법사를 사용하여 이 패키지를 만들 수 있습니다. 자세한 내용은 [Azure Cloud Services 및 ASP.NET으로 시작하기](http://go.microsoft.com/fwlink/p/?LinkID=623089)를 참조하세요.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| Position |named |
| 기본값 |없음 |
| Accept Pipeline Input? |False |
| Accept Wildcard Characters? |False |

## <a name="databaseserverpassword"></a>DatabaseServerPassword
Azure에서 SQL 데이터베이스의 사용자 이름 및 암호입니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| Position |named |
| 기본값 |없음 |
| Accept Pipeline Input? |False |
| Accept Wildcard Characters? |False |

## <a name="sendhostmessagestooutput"></a>SendHostMessagesToOutput
True이면 스크립트에서 출력 스트림으로 메시지를 프린트합니다.

| 매개 변수 | 기본값 |
| --- | --- |
| 별칭 |없음 |
| 필수 여부 |False |
| Position |named |
| 기본값 |False |
| Accept Pipeline Input? |False |
| Accept Wildcard Characters? |False |

## <a name="remarks"></a>설명
스크립트를 사용하여 개발 및 테스트 환경을 만드는 방법에 대한 전체 설명은 [Windows PowerShell 스크립트를 사용하여 개발 및 테스트 환경에 게시](vs-azure-tools-publishing-using-powershell-scripts.md)를 참조하세요.

JSON 구성 파일은 배포될 내용의 세부 정보를 지정합니다. 해당 웹 사이트의 이름 및 사용자 이름과 같은 프로젝트를 만들 때 지정된 정보를 포함합니다. 있는 경우 프로비전할 새 데이터베이스도 포함합니다. 다음 코드에서는 JSON 구성 파일을 예로 보여줍니다.

    {
        "environmentSettings": {
            "webSite": {
                "name": "WebApplication10554",
                "location": "West US"
            },
            "databases": [
                {
                    "connectionStringName": "DefaultConnection",
                    "databaseName": "WebApplication10554_db",
                    "serverName": "iss00brc88",
                    "user": "sqluser2",
                    "password": "",
                    "edition": "",
                    "size": "",
                    "collation": "",
                    "location": "West US"
                }
            ]
        }
    }

배포된 내용을 변경하도록 JSON 구성 파일을 편집할 수 있습니다. 웹 사이트 섹션은 필수이지만 데이터 섹션은 선택 사항입니다.

## <a name="next-steps"></a>다음 단계
자세한 내용은 [Publish-WebApplicationVM(Windows PowerShell 스크립트)](vs-azure-tools-publish-webapplicationvm.md)
