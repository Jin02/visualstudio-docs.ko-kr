---
title: 속성이 연결에 참여하고 있으므로 이 속성을 삭제할 수 없음
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: e1890535fb008c8e8be6ee9dea0eda3ab3844da6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648151"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>&lt;property name&gt; 속성은 &lt;association name&gt; 연결에 참여하고 있으므로 삭제할 수 없음

선택한 속성이 오류 메시지에 표시된 클래스 간 연결의 **연결 속성**으로 설정되었습니다. 속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.

**연결 속성**을 데이터 클래스의 다른 속성으로 설정하면 원하는 속성을 삭제할 수 있습니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. **O/R 디자이너**에서 오류 메시지에 표시된 데이터 클래스를 연결하는 연결 선을 선택합니다.

2. 해당 선을 두 번 클릭하여 **연결 편집기** 대화 상자를 엽니다.

3. **연결 속성**에서 속성을 제거합니다.

4. 속성 삭제를 다시 한 번 시도합니다.

## <a name="see-also"></a>참조

- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)