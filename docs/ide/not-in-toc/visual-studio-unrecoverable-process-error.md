---
title: 프로세스에서 복구할 수 없는 오류 발생
ms.date: 06/22/2018
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d1879be46498d851eec0fbfce71b2328bdfc9afb
ms.sourcegitcommit: b4e0cc76d94fe8cf6d238c4cc09512d17131a195
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81224442"
---
# <a name="visual-studio-unrecoverable-process-error"></a>Visual Studio 복구할 수 없는 프로세스 오류

Visual Studio에서는 여러 out-of-proc 프로세스를 사용하여 필요한 백그라운드 작업을 실행합니다(예: Live Unit Testing, 코드 분석기 등). Visual Studio에서 이러한 out-of-proc 프로세스를 실행하면 성능상 이점이 있습니다. 예를 들어 리소스를 많이 사용하는 장기 작업을 실행할 때 더 빠르게 응답합니다. 또한 Visual Studio는 32비트 프로세스이므로 out-of-proc 프로세스를 실행하면 메모리 집약적인 작업을 수행할 때 더 많은 메모리 공간이 확보됩니다.

어떤 이유로 *ServiceHub.RoslynCodeAnalysisService.exe* 또는 *ServiceHub.RoslynCodeAnalysisService32.exe* 프로세스가 종료되면 다음 메시지와 함께 팝업 정보 표시줄이 나타납니다.

**"Visual Studio에서 사용하는 프로세스에서 복원할 수 없는 오류가 발생했습니다. 작업을 저장하고, Visual Studio를 종료한 후 다시 시작하는 것을 권장해 드립니다."**

이 메시지가 표시되는 경우 작업을 저장하고 Visual Studio를 종료한 후 다시 시작해야 합니다.

## <a name="list-of-processes"></a>프로세스 목록

다음은 Visual Studio에서 사용하는 out-of-proc 프로세스의 목록입니다. 이 목록에는 특정 워크플로 또는 시나리오에서 시작되는 프로세스가 포함되므로 대부분의 경우 모든 프로세스가 동시에 실행되지 않습니다.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- PerfWatson2.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.VSDetouredHost.exe
- WaAppAgent.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe

이러한 프로세스 중 하나가 예기치 않게 종료되면 Visual Studio 내의 일부 기능이 작동하지 않습니다. 일부 프로세스의 경우 기능 손실이 사소할 수 있습니다. 다른 경우 Visual Studio의 안정성이 영향을 받고 오류 메시지가 표시됩니다.
