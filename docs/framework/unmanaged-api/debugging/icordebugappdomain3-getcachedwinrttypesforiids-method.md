---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 601110d37fabbff01aeb14d8ca69a27a2463353f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491419"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드
캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식은 응용 프로그램 도메인에서 해당 인터페이스 식별자 기반으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cReqTypes`  
 [in] 필요한 형식의 수입니다.  
  
 `iidsToResolve`  
 [in] 관리 되는 표현에 해당 하는 인터페이스 식별자를 포함 하는 배열에 대 한 포인터를 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 검색할 형식입니다.  
  
 `ppTypesEnum`  
 [out] 캐시 된 열거 수 있도록 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대 한 포인터의 표현을 관리 합니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 의 인터페이스 식별자에 따라 형식 검색 `iidsToResolve`합니다.  
  
## <a name="remarks"></a>설명  
 메서드를 특정 인터페이스 식별자에 대 한 정보를 검색 하지 못하는 경우 "ICorDebugTypeEnum" 컬렉션의 해당 항목은 형식이 `ELEMENT_TYPE_END` 데이터 검색 문제로 인해 오류 또는 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스에 대 한 식별자입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorDebugAppDomain3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
