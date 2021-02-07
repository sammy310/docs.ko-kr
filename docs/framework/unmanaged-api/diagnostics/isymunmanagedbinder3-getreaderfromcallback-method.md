---
description: '자세히 알아보기: ISymUnmanagedBinder3:: GetReaderFromCallback 메서드'
title: ISymUnmanagedBinder3::GetReaderFromCallback 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: ba7c819678fee7625f3cddb29d99f5d7f4c6f991
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689874"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback 메서드

사용자가 또는를 사용 하 여를 구현 하거나 제공 하 여 `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` 메모리에서 디버그 디렉터리 정보를 가져올 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
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
  
 `callback`  
 진행 콜백 함수에 대 한 포인터입니다.  
  
 `pRetVal`  
 제한이 반환 된 [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface로 설정 된 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedBinder3 인터페이스](isymunmanagedbinder3-interface.md)
