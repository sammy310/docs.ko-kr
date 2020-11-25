---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707089"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드

비동기 작업을 시작 하는 시작 메서드를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>반환 값  

 `HRESULT`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)
