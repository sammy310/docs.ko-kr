---
description: '자세히 알아보기: ISymUnmanagedBinder2:: GetReaderForFile2 메서드'
title: ISymUnmanagedBinder2::GetReaderForFile2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
ms.openlocfilehash: c1a180ceec07c3087150613365acfce646adc34e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689939"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2 메서드

메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.  
  
 이 메서드는 [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) 메서드 보다 더 광범위 한 PDB (프로그램 데이터베이스) 파일 검색을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  

 `importer`  
 진행 메타 데이터 가져오기 인터페이스에 대 한 포인터입니다.  
  
 `fileName`  
 진행 파일 이름에 대 한 포인터입니다.  
  
 `searchPath`  
 진행 검색 경로에 대 한 포인터입니다.  
  
 `searchPolicy`  
 진행 기호 판독기를 검색할 때 사용할 정책을 지정 하는 [Corsymsearchpolicyattributes](corsymsearchpolicyattributes-enumeration.md) 열거형의 값입니다.  
  
 `pRetVal`  
 제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="remarks"></a>설명  

 이 버전의 메서드는 모듈 바로 옆의 영역에서 PDB 파일을 검색할 수 있습니다. [Corsymsearchpolicyattributes](corsymsearchpolicyattributes-enumeration.md)를 결합 하 여 검색 정책을 제어할 수 있습니다. 예를 들어은 `AllowReferencePathAccess | AllowSymbolServerAccess` 실행 파일 및 기호 서버 옆에 있는 PDB를 찾지만 레지스트리를 쿼리하거나 실행 파일의 경로를 사용 하지 않습니다. `searchPath`매개 변수가 제공 되는 경우 해당 디렉터리는 항상 검색 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedBinder2 인터페이스](isymunmanagedbinder2-interface.md)
- [GetReaderForFile 메서드](isymunmanagedbinder-getreaderforfile-method.md)
