---
title: 쿼리. Pdb 파일 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68efbd59abe1b0aff717a55383f3ac330586164a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72738576"
---
# <a name="querying-the-pdb-file"></a>.Pdb 파일 쿼리
프로그램 데이터베이스 파일 (확장명 .pdb)은 프로젝트를 컴파일하고 연결 하는 과정에서 수집 된 형식 및 기호화 된 디버깅 정보를 포함 하는 이진 파일입니다. PDB 파일은 **/debug** 옵션을 사용 하 여 **/zi** 또는C++ **/zi** 나 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] 프로그램을 사용 하 여 C/프로그램을 컴파일할 때 생성 됩니다. 개체 파일에는 디버깅 정보를 위한 .pdb 파일에 대 한 참조가 포함 되어 있습니다. Pdb 파일에 대 한 자세한 내용은 [Pdb 파일](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yd4f8bd1(v=vs.100))을 참조 하세요. DIA 응용 프로그램은 다음과 같은 일반적인 단계를 사용 하 여 실행 가능한 이미지 내의 다양 한 기호, 개체 및 데이터 요소에 대 한 세부 정보를 가져올 수 있습니다.

### <a name="to-query-the-pdb-file"></a>.Pdb 파일을 쿼리하려면

1. [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) 인터페이스를 만들어 데이터 소스를 가져옵니다.

    ```C++
    CComPtr<IDiaDataSource> pSource;
    hr = CoCreateInstance( CLSID_DiaSource,
                           NULL,
                           CLSCTX_INPROC_SERVER,
                           __uuidof( IDiaDataSource ),
                          (void **) &pSource);

    if (FAILED(hr))
    {
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );
    }
    ```

2. [IDiaDataSource:: loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) 또는 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 를 호출 하 여 디버깅 정보를 로드 합니다.

    ```C++
    wchar_t wszFilename[ _MAX_PATH ];
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )
    {
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )
        {
            Fatal( "loadDataFromPdb/Exe" );
        }
    }
    ```

3. [IDiaDataSource:: openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 을 호출 하 여 디버깅 정보에 대 한 액세스 권한을 얻을 수 있도록 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 를 엽니다.

    ```C++
    CComPtr<IDiaSession> psession;
    if ( FAILED( pSource->openSession( &psession ) ) )
    {
        Fatal( "openSession" );
    }
    ```

4. @No__t_0의 메서드를 사용 하 여 데이터 소스에서 기호를 쿼리할 수 있습니다.

    ```C++
    CComPtr<IDiaSymbol> pglobal;
    if ( FAILED( psession->get_globalScope( &pglobal) ) )
    {
        Fatal( "get_globalScope" );
    }
    ```

5. @No__t_0 인터페이스를 사용 하 여 디버그 정보의 기호나 기타 요소를 열거 하 고 검색 합니다.

    ```C++
    CComPtr<IDiaEnumTables> pTables;
    if ( FAILED( psession->getEnumTables( &pTables ) ) )
    {
        Fatal( "getEnumTables" );
    }
    CComPtr< IDiaTable > pTable;
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )
    {
        // Do something with each IDiaTable.
    }
    ```

## <a name="see-also"></a>참조
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)
