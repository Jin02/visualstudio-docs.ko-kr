---
title: 템플릿 디렉터리 설명 (합니다. Vsdir) 파일 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsdir files
- VSDIR files
- template directory description files
ms.assetid: 9df51800-190e-4662-b685-fdaafcff1400
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89152fcb003886087704107f2d4c2a66d3313cc3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62857753"
---
# <a name="template-directory-description-vsdir-files"></a>템플릿 디렉터리 설명(.Vsdir) 파일
템플릿 디렉터리 설명 (.vsdir) 파일은 통합된 개발 환경 (IDE) 폴더, 마법사.vsz 파일 및 대화 상자에서 프로젝트와 연결 된 템플릿 파일을 표시할 수 있도록 하는 텍스트 파일입니다. 콘텐츠 파일 또는 폴더당 하나의 레코드를 포함합니다. 참조 된 위치에 모든.vsdir 파일 하나만.vsdir 파일 여러 폴더, 마법사 또는 템플릿 파일을 설명 하기 위해 일반적으로 제공 되지만 병합 됩니다.

 .Vsdir 파일.vsdir 파일 자체에 참조 되는 파일 폴더 (하위)은 모든 동일한 디렉터리에 있습니다. IDE 마법사를 실행 또는 표시 폴더 또는 파일의 경우는 **새 프로젝트** 하거나 **새 항목 추가** IDE.vsdir 파일 인지 여부를 확인 하려면 실행 파일이 있는 디렉터리를 검사 대화 상자 존재 합니다. .Vsdir 파일을 발견할 경우 실행 또는 표시 폴더 또는 파일에 대 한 항목이 포함 되어 있는지 확인 하는 IDE를 읽습니다. 항목이 발견 되는 경우 IDE는 정보를 사용 하 여 마법사 실행 또는 콘텐츠 표시 합니다.

 SourceFiles.vsdir 파일에서 다음 코드 예제는에 \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems\Source_Files 레지스트리 키:

```
HeaderFile.h|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#125|130|#126|0|0|0|#127
SourceFile.cpp|{E59935A1-6156-11d1-87A6-00A0C91E2A46}|#122|110|#123|0|0|0|#124
```

 이 경우 두 레코드의에서 경우 하나의 파일 새 줄 (캐리지 리턴 문자)는 각 레코드를 구분합니다. 각 줄에는 다른 파일 형식을 나타냅니다. 파이프 (&#124;) 문자는 각 레코드에서 필드를 구분 합니다. 단일 디렉터리에 있는 다른 파일 이름을 가진 여러.vsdir 파일 포함 하거나 각 파일 형식에 대 한 하나의.vsdir 파일 할 수 있습니다.

## <a name="fields"></a>필드
 다음 표에서 각 레코드에 대해 지정 된 필드를 나열 합니다.

| 필드 | 설명 |
| - | - |
| 상대 경로 이름 (RelPathName) | HeaderFile.h 등 MyWizard.vsz 폴더, 템플릿 또는.vsz 파일의 이름입니다. 이 필드에 폴더를 나타내는 데 사용 되는 이름을 수도 있습니다. |
| {clsidPackage} | 에서 지역화 된 문자열을 LocalizedName, 설명, IconResourceId, 및 SuggestedBaseName와 같은 VSPackage의 위성 동적 연결 라이브러리 (DLL) 리소스에 액세스할 수 있도록 하는 VSPackage의 GUID입니다. IconResourceId는 DLLPath 제공 되지 않으면 적용 됩니다. **참고:**  이전 필드 중 하나 이상의 리소스 식별자가 아닌 경우이 필드는 선택 사항입니다. 이 필드는 해당 텍스트를 지역화 하지 않습니다는 제 3 자 마법사를 사용 하 여 해당.vsdir 파일 일반적으로 비어 있습니다. |
| LocalizedName | 마법사 템플릿 파일의 지역화 된 이름입니다. 이 필드는 문자열 또는 폼 "#ResID"의 리소스 식별자를 수 있습니다. 이 이름이 표시 됩니다는 **새 항목 추가** 대화 상자. **참고:**  LocalizedName 리소스 식별자 인 경우 {0} clsidPackage}가 필요 합니다. |
| SortPriority | 이 템플릿 파일 또는 마법사의 상대적 우선 순위를 나타내는 정수입니다. 예를 들어이 항목에 값 1의 경우이 항목이 항목 옆에 있는 다른 값을 사용 하 여 1 및 2 이상은 정렬 값을 사용 하 여 모든 항목 미리 표시 됩니다.<br /><br /> 정렬 우선 순위 항목을 동일한 디렉터리에 상대적입니다. 동일한 디렉터리에 둘 이상의.vsdir 파일 있을 수 있습니다. 이런 경우, 모든 항목 <em>.</em> vsdir 파일을 해당 디렉터리에 병합 됩니다. 우선 순위가 같은 항목 표시 이름의 대/소문자 사전적 순서 대로 나열 됩니다. `_wcsicmp` 함수를 사용 하는 항목을 정렬 합니다.<br /><br /> .Vsdir 파일에 설명 되지 않은 항목에 우선 순위 번호를.vsdir 파일에 나열 된 가장 높은 우선 순위 번호 보다 큰 포함 됩니다. 결과 이러한 항목 이름에 관계 없이 표시 되는 목록 끝에 있습니다. |
| 설명 | 마법사 템플릿 파일의 지역화 된 설명입니다. 이 필드는 문자열 또는 폼 "#ResID"의 리소스 식별자를 수 있습니다. 이 문자열에 표시 됩니다는 **새 프로젝트** 또는 **새 항목 추가** 대화 상자 항목을 선택 합니다. |
| DLLPath 또는 {clsidPackage} | 템플릿 파일 또는 마법사에 대 한 아이콘을 로드 하는 데 사용 합니다. 아이콘은.dll 또는.exe 파일을 리소스로 IconResourceId를 사용 하 여 로드 됩니다. 이.dll 또는.exe 파일 또는 전체 경로 사용 하 여 VSPackage의 GUID를 사용 하 여 식별할 수 있습니다. 구현은 VSPackage의 DLL (없습니다: 위성 DLL) 아이콘을 로드할 사용 됩니다. |
| IconResourceId | DLL 또는 VSPackage 구현 표시할 아이콘을 결정 하는 DLL의에서 리소스 식별자입니다. |
| 플래그 (<xref:Microsoft.VisualStudio.Shell.Interop.__VSDIRFLAGS>) | 사용 하지 않거나 사용 하도록 설정 하는 데 사용 합니다 **이름** 및 **위치** 필드에 **새 항목 추가** 대화 상자. 값을 **플래그** 필드는 필수 비트 플래그의 조합을 10 진수로 변환 합니다.<br /><br /> 사용자에 항목을 선택 하는 경우는 **새로 만들기** 탭, 프로젝트 표시 여부를 결정 이름 필드 및 위치 필드는 때를 **새 항목 추가** 대화 상자가 먼저 표시 됩니다. 항목을.vsdir 파일을 통해 제어할 수 있습니다만 항목이 선택 될 때 필드 사용 안 함 및 사용 되는지 여부를 합니다. |
| SuggestedBaseName | 파일, 마법사 또는 서식 파일에 대 한 기본 이름을 나타냅니다. 이 필드는 문자열 또는 폼 "#ResID"의 리소스 식별자입니다. IDE는 항목에 대 한 기본 이름을 제공 하기 위해이 값을 사용 합니다. 이 기준 값 이름을 MyFile21.asp 같은 고유 하 게 하는 정수 값을 사용 하 여 추가 됩니다.<br /><br /> 위 목록에 대 한 설명, DLLPath, IconResourceId, 플래그 및 SuggestedBaseNumber 템플릿과 마법사 파일에만 적용 됩니다. 이러한 필드 폴더에 적용 되지 않습니다. 이 팩트 BscPrjProjectItems 파일에서 코드 처럼는 \<EnvSDK > \BscPrj\BscPrj\BscPrjProjectItems 레지스트리 키입니다. 이 파일에는 각 레코드에 대 한 4 개의 필드를 사용 하 여 (각 폴더에 대해 하나)는 세 개의 레코드가 포함 됩니다. RelPathName, {clsidPackage} LocalizedName, 및 SortPriority 합니다.<br /><br /> `General&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#110&#124;100`<br /><br /> `Source_Files&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#111&#124;110`<br /><br /> `Env&#124;{E59935A1-6156-11d1-87A6-00A0C91E2A46}&#124;#112&#124;120` |

 마법사 파일을 만들 때 다음 사항을 고려해 야 합니다.

- 의미 있는 데이터가 없는 모든 선택적 필드는 0 (영) 자리 표시자로 포함 해야 합니다.

- 제공 된 지역화 된 이름이 없는 경우에 상대 경로 이름은 마법사 파일에 사용 됩니다.

- DLLPath clsidPackage 아이콘 위치를 재정의합니다.

- 정의 된 아이콘이 없는 경우 IDE는 해당 확장명을 가진 파일에 대 한 기본 아이콘을 사용 합니다.

- 기본 이름이 없는 제공 하는 경우 'Project' 사용 됩니다.

- .Vsz 파일, 폴더 또는 템플릿 파일을 삭제 하면.vsdir 파일에서 연결 된 해당 레코드도 제거 해야 합니다.

## <a name="see-also"></a>참고 항목
- [마법사](../../extensibility/internals/wizards.md)
- [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)