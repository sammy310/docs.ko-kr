---
title: ISymUnmanagedWriter::SetUserEntryPoint 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650728"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a>ISymUnmanagedWriter::SetUserEntryPoint 메서드
이 모듈에 대 한 진입점을 되는 사용자 정의 메서드를 지정 합니다. 예를 들어이 진입점에는 main 전에 컴파일러에서 생성 된 스텁이 대신 사용자의 기본 메서드 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a>매개 변수  
 `entryMethod`  
 [in] 사용자 진입점인 메서드의 메타 데이터 토큰을 가리킵니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
