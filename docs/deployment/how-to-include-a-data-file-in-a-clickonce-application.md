---
title: '방법: Include a Data File in a ClickOnce Application | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, data
- deploying applications [ClickOnce], data files
- data access, ClickOnce applications
ms.assetid: 89ee46ef-bc8c-4ab0-a2ac-1220f9da06fc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd2db09937ad76c0ea4c990fcdba5c34a0f8f66c
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60093880"
---
# <a name="how-to-include-a-data-file-in-a-clickonce-application"></a>방법: ClickOnce 애플리케이션에 데이터 파일 포함
각 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치한 응용 프로그램 데이터 디렉터리는 응용 프로그램의 고유한 데이터를 관리할 수 있는 대상 컴퓨터의 로컬 디스크에 할당 됩니다. 데이터 파일의 파일 형식 포함할 수 있습니다: 텍스트 파일, XML 파일 또는 심지어 Microsoft Access 데이터베이스 (*.mdb*) 파일입니다. 다음 절차에서는 임의의 형식으로의 데이터 파일을 추가 하는 방법에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.

### <a name="to-include-a-data-file-by-using-mageexe"></a>Mage.exe를 사용 하 여 데이터 파일을 포함 하려면

1. 응용 프로그램 파일의 나머지 부분을 사용 하 여 응용 프로그램 디렉터리에 데이터 파일을 추가 합니다.

    일반적으로 응용 프로그램 디렉터리 배포의 현재 버전을 사용 하 여 레이블이 지정 된 디렉터리 됩니다-예를 들어 v1.0.0.0 합니다.

2. 데이터 파일을 나열 하 여 응용 프로그램 매니페스트를 업데이트 합니다.

    `mage -u v1.0.0.0\Application.manifest -FromDirectory v1.0.0.0`

    이 태스크를 수행할 다시 응용 프로그램 매니페스트에 파일 목록을 만들고 해시 서명을 자동으로 생성 합니다.

3. 원하는 텍스트 편집기나 XML 편집기에서 응용 프로그램 매니페스트를 열고 찾습니다는 `file` 최근에 추가 된 파일에 대 한 요소입니다.

    이라는 XML 파일을 추가한 경우 `Data.xml`, 파일은 다음 코드 예와 유사 합니다.

   `<file name="Data.xml" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`

4. 특성을 추가 합니다 `type` 이 요소에 값을 사용 하 여 제공 `data`합니다.

   `<file name="Data.xml" writeableType="applicationData" hash="23454C18A2DC1D23E5B391FEE299B1F235067C59" hashalg="SHA1" asmv2:size="39500" />`

5. 에 키 쌍 또는 인증서를 사용 하 여 응용 프로그램 매니페스트에 다시 서명 및 배포 매니페스트에 다시 서명 합니다.

    응용 프로그램 매니페스트의 해시가 변경 되었기 때문에 배포 매니페스트에 다시 서명 해야 합니다.

    `mage -s app manifest -cf cert_file -pwd password`

    `mage -u deployment manifest -appm app manifest`

    `mage -s deployment manifest -cf certfile -pwd password`

### <a name="to-include-a-data-file-by-using-mageuiexe"></a>MageUI.exe를 사용 하 여 데이터 파일을 포함 하려면

1. 응용 프로그램 파일의 나머지 부분을 사용 하 여 응용 프로그램 디렉터리에 데이터 파일을 추가 합니다.

2. 일반적으로 응용 프로그램 디렉터리 배포의 현재 버전을 사용 하 여 레이블이 지정 된 디렉터리 됩니다-예를 들어 v1.0.0.0 합니다.

3. 에 **파일** 메뉴에서 클릭 **엽니다** 여 응용 프로그램 매니페스트를 엽니다.

4. 선택 된 **파일** 탭 합니다.

5. 탭의 맨 위에 있는 텍스트 상자에 응용 프로그램의 파일을 포함 하는 디렉터리를 입력 한 다음 클릭 **채우기**합니다.

     데이터 파일 표에 표시 됩니다.

6. 설정 된 **파일 형식** 데이터 파일의 값 **데이터**입니다.

7. 응용 프로그램 매니페스트를 저장 하 고 파일에 다시 서명 합니다.

     *MageUI.exe* 파일에 다시 서명 하 라는 메시지가 표시 됩니다.

8. 배포 매니페스트에 다시 서명

     응용 프로그램 매니페스트의 해시가 변경 되었기 때문에 배포 매니페스트에 다시 서명 해야 합니다.

## <a name="see-also"></a>참고자료
- [ClickOnce 애플리케이션의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)