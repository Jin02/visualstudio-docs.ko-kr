---
title: -LCID(devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /L switch
- Devenv, /LCID switch
- locale IDs
- L Devenv switch
- /L Devenv switch
- LCID devenv switch
- /LCID Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 80c4af137edc80166d6a652c676d5607d8c2328d
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75595529"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)

IDE 내의 텍스트, 통화 및 다른 값에 사용된 기본 언어를 설정합니다.

## <a name="syntax"></a>구문

```shell
devenv {/LCID|/L} LocaleID
```

## <a name="arguments"></a>인수

- *LocaleID*

  필수 요소. 지정한 언어의 로캘 식별자(LCID)입니다.

## <a name="remarks"></a>설명

IDE를 로드하고 환경에 대한 기본 자연 언어를 설정합니다. 이 변경은 세션 간에 지속되며, IDE는 **도구** > **옵션** > **환경** > **국가별 설정** > **언어** 상자에 이 변경을 표시합니다.

지정된 언어를 사용자의 시스템에서 사용할 수 없는 경우 `/LCID` 스위치는 무시됩니다.

다음 표에서는 Visual Studio에서 지원하는 언어의 LCID 목록을 보여 줍니다.

|언어|LCID|
|--------------|----------|
|및|2052|
|옵션 대신,|1028|
|영어|1033|
|프랑스어|1036|
|독일어|1031|
|이탈리아어|1040|
|일본어|1041|
|한국어|1042|
|스페인어|3082|

## <a name="example"></a>예제

이 예에서는 영어 리소스 문자열을 사용하는 IDE를 로드합니다.

```shell
devenv /LCID 1033
```

## <a name="see-also"></a>참조

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
- [옵션 대화 상자, 환경, 국가별 설정](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [창 레이아웃 사용자 지정](../../ide/customizing-window-layouts-in-visual-studio.md)
