---
title: 용 Data toolsC++
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CPP
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
- cplusplus
ms.openlocfilehash: 2be19729b61831e6f15ff40b6b4e1d7b4b0bb541
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586057"
---
# <a name="visual-studio-data-tools-for-c"></a>C++용 Visual Studio 데이터 도구

Native C++ 는 데이터 원본에 액세스할 때 가장 빠른 성능을 제공 하는 경우가 많습니다. 그러나 Visual Studio의 응용 C++ 프로그램에 대 한 데이터 도구는 .net 응용 프로그램에 비해 다양 한 기능이 아닙니다. 예를 들어 데이터 **소스 창을 사용** 하 여 데이터 원본을 C++ 디자인 화면으로 끌어서 놓을 수는 없습니다. 개체 관계형 계층이 필요한 경우에는 직접 작성 하거나 타사 제품을 사용 해야 합니다. Microsoft Foundation Class 라이브러리를 사용 하는 응용 프로그램은 문서 및 뷰와 함께 일부 데이터베이스 클래스를 사용 하 여 메모리에 데이터를 저장 하 고 사용자에 게 표시할 수 있지만, 데이터 바인딩 기능 에서도 마찬가지입니다. 자세한 내용은 [시각적 개체 C++의 데이터 액세스 ](/cpp/data/data-access-in-cpp)를 참조 하세요.

SQL 데이터베이스에 연결 하기 위해 네이티브 C++ 응용 프로그램은 Windows에 포함 된 ODBC 및 OLE DB 드라이버와 ADO 공급자를 사용할 수 있습니다. 이러한 인터페이스를 지 원하는 모든 데이터베이스에 연결할 수 있습니다. ODBC 드라이버는 표준입니다. OLE DB은 이전 버전과의 호환성을 위해 제공 됩니다. 이러한 데이터 기술에 대 한 자세한 내용은 [Windows Data Access 구성 요소](/previous-versions/windows/desktop/ms692897(v=vs.85))를 참조 하세요.

SQL Server 2005 이상에서 사용자 지정 기능을 활용 하려면 [SQL Server native client](/sql/relational-databases/native-client/sql-server-native-client)를 사용 합니다. Native client에는 하나의 네이티브 DLL (동적 연결 라이브러리)에 SQL Server ODBC 드라이버와 SQL Server OLE DB 공급자도 포함 되어 있습니다. 이러한 코드는 네이티브 코드 Api (ODBC, OLE DB 및 ADO)를 사용 하 여 Microsoft SQL Server 하는 응용 프로그램을 지원 합니다. SQL Server Native Client SQL Server Data Tools와 함께 설치 됩니다. 프로그래밍 가이드는 [SQL Server native client 프로그래밍](/sql/relational-databases/native-client/sql-server-native-client-programming)을 참조 하세요.

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>ODBC를 통해 localDB에 연결 하 고 C++ 응용 프로그램에서 SQL Native Client 하려면

1. SQL Server 데이터 도구를 설치합니다.

2. 에 연결할 샘플 SQL 데이터베이스가 필요한 경우 Northwind 데이터베이스를 다운로드 하 고 새 위치에 압축을 풉니다.

3. SQL Server Management Studio를 사용 하 여 압축을 푼 *Northwind .mdf* 파일을 localDB에 연결 합니다. SQL Server Management Studio 시작 되 면 (localdb) \MSSQLLocalDB.에 연결 합니다.

   ![SSMS 연결 대화 상자](../data-tools/media/raddata-ssms-connect-dialog.png)

   그런 다음 왼쪽 창에서 localdb 노드를 마우스 오른쪽 단추로 클릭 하 고 **연결**을 선택 합니다.

   ![SSMS 데이터베이스 연결](../data-tools/media/raddata-ssms-attach-database.png)

4. ODBC Windows SDK 샘플을 다운로드 하 고 새 위치에 압축을 풉니다. 이 예제에서는 데이터베이스에 연결 하 고 쿼리 및 명령을 실행 하는 데 사용 되는 기본 ODBC 명령을 보여 줍니다. [MICROSOFT ODBC (Open Database Connectivity)](/sql/odbc/microsoft-open-database-connectivity-odbc)에서 이러한 함수에 대해 자세히 알아볼 수 있습니다. 솔루션을 처음 로드할 때 ( C++ 폴더에 있는 경우) visual studio에서 솔루션을 현재 버전의 visual studio로 업그레이드 하도록 제공 합니다. **예**를 클릭합니다.

5. Native client를 사용 하려면 *헤더* 파일 및 *lib* 파일이 필요 합니다. 이러한 파일에는 SQL .h에 정의 된 ODBC 함수 외에도 SQL Server 관련 된 함수와 정의가 포함 되어 있습니다. **Project** > **속성** > **VC + + 디렉터리**에 다음 포함 디렉터리를 추가 합니다.

   **%ProgramFiles%\Microsoft SQL Server\110\SDK\Include**

   그리고이 라이브러리 디렉터리는 다음과 같습니다.

   **%ProgramFiles%\Microsoft SQL Server\110\SDK\Lib**

6. *Odbcsql*에 다음 줄을 추가 합니다. #Define는 관련이 없는 OLE DB 정의가 컴파일될 수 없도록 합니다.

   ```cpp
   #define _SQLNCLI_ODBC_
   #include <sqlncli.h>
   ```

    샘플은 실제로 native client 기능을 사용 하지 않으므로 컴파일 및 실행을 위해 앞의 단계를 수행 하지 않아도 됩니다. 그러나 이제이 기능을 사용할 수 있도록 프로젝트가 구성 되어 있습니다. 자세한 내용은 [SQL Server Native Client 프로그래밍](/sql/relational-databases/native-client/sql-server-native-client)을 참조하세요.

7. ODBC 하위 시스템에서 사용할 드라이버를 지정 합니다. 이 샘플은의 드라이버 연결 문자열 특성을 명령줄 인수로 전달 합니다. **디버깅** > **프로젝트** > **속성** 에서 다음 명령 인수를 추가 합니다.

   ```cpp
   DRIVER="SQL Server Native Client 11.0"
   ```

8. **F5** 키를 눌러 애플리케이션을 빌드하고 실행합니다. 데이터베이스를 입력 하 라는 메시지가 표시 되는 드라이버의 대화 상자가 표시 됩니다. `(localdb)\MSSQLLocalDB`를 입력 하 고 **트러스트 된 연결 사용**을 선택 합니다. **확인**을 누릅니다. 연결에 성공 했음을 나타내는 메시지가 포함 된 콘솔이 표시 되어야 합니다. 또한 SQL 문을 입력할 수 있는 명령 프롬프트가 표시 되어야 합니다. 다음 화면에는 예제 쿼리와 결과가 나와 있습니다.

   ![ODBC 샘플 쿼리 출력](../data-tools/media/raddata-odbc-sample-query-output.png)

## <a name="see-also"></a>참조

- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)
