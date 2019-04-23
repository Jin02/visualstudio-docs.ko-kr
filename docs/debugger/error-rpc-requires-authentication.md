---
title: '오류: RPC에 인증이 필요 합니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.rpc_requires_authentication
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c473916a6b689984f234736eb8b763056fc002d9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60092008"
---
# <a name="error-rpc-requires-authentication"></a>오류: RPC에 인증 필요
Visual Studio 디버거에서 원격 컴퓨터에 연결할 수 없습니다. 로컬 컴퓨터에서 RPC 정책을 사용하도록 설정되어 있어 원격 디버깅을 수행할 수 없습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 실행할 `\` *windir*`\system32\regedt32.exe`

2. 찾아 삭제 `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows NT\RPC\RestrictRemoteClients`합니다.

3. 컴퓨터를 다시 시작하여 레지스트리 변경 내용을 적용합니다.

4. 문제가 지속 되 면에 대 한 도메인 관리자에 게 문의 합니다 **컴퓨터 구성 > 관리 템플릿 > 시스템 > 원격 프로시저 호출 > 인증 되지 않은 RPC 클라이언트 제한** 그룹 정책 설정입니다.