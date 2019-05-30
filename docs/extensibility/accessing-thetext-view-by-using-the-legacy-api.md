---
title: 레거시 API를 사용 하 여 텍스트 보기에 액세스 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a52ba7fa7e57e63f13cfe502a46d54071ee82591
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313671"
---
# <a name="access-the-text-view-by-using-the-legacy-api"></a>기존 API를 사용 하 여 텍스트 보기에 액세스
텍스트 뷰는 텍스트 버퍼에 저장 되는 텍스트를 표시 합니다. 다음 섹션에 나와 있는 것 처럼 기존 API를 사용 하 여 텍스트 보기에 액세스할 수 있습니다.

## <a name="text-view-object"></a>텍스트 뷰 개체
 뷰는 데이터 버퍼에 대 한 창 및 각 뷰에 자체 텍스트 버퍼를 사용 하 여 연결 됩니다. 다음 다이어그램으로 표현 되는 텍스트 뷰 개체의 키 인터페이스를 보여 줍니다. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>합니다.

 ![Visual Studio 텍스트 뷰 개체](../extensibility/media/vstextview.gif)

 뷰는 버퍼에 텍스트를 표시 하는 방법. 보기에 표시 되지 않도록 버퍼에 있는 텍스트의 정확한 표시 개요, 자동 줄 바꿈 등의 기능을 포함 합니다.

 뷰를 다른 서비스 또는 프로세스를 들어오는 명령을 가로채서 보기 여 작업을 수행 하기 전에 해당 작업할 수 있습니다. 이렇게 하려면 가장 일반적인 서비스는 언어 서비스입니다. 예를 들어 언어 서비스 ENTER 키를 들여쓰기으로 실행 되는 사용자 지정 동작이 나 도구 팁을 제공 하는 명령은 가로채기 위해 해야 할 수 있습니다.

## <a name="add-functionality-to-the-text-view"></a>텍스트 보기에 기능 추가
 특정 키 입력을 처리 하 여 텍스트 보기 동작을 사용자 지정할 수 있습니다. 구현 하는 키 입력을 가로채 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> 개체를 명령 대상을 제공 하 고 (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) 모니터 및 절편 명령에 있습니다.

 텍스트 뷰 명령 필터에 대 한 순차적 아키텍처를 사용합니다. 새 명령 필터 (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 개체)를 호출 하 여 시퀀스에 추가 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> 메서드.

 텍스트 보기에 대 한 이벤트 알림을 사용 하 여 제공 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents> 인터페이스입니다. 텍스트 뷰 변경 알림을 수신 하려면 클라이언트 개체에서이 인터페이스를 구현 합니다. 사용 하 여 텍스트 보기에이 인터페이스를 노출 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 보기에서 변경 알림을 수신 하도록 텍스트 보기에는 인터페이스입니다.

## <a name="see-also"></a>참고자료

- [기존 API를 사용 하 여 보기 설정 변경](../extensibility/changing-view-settings-by-using-the-legacy-api.md)
- [전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여](../extensibility/using-the-text-manager-to-monitor-global-settings.md)