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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179059"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs 메서드
인터페이스 식별자를 기반으로 응용 프로그램 도메인에서 캐시된 Windows 런타임 형식에 대한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cReqTypes`  
 【인】 필수 형식의 수입니다.  
  
 `iidsToResolve`  
 【인】 검색할 Windows 런타임 형식의 관리되는 표현에 해당하는 인터페이스 식별자가 포함된 배열에 대한 포인터입니다.  
  
 `ppTypesEnum`  
 【아웃】 `iidsToResolve`의 인터페이스 식별자를 기반으로 검색된 Windows 런타임 형식의 캐시된 관리되는 표현을 열거할 수 있는 "ICorDebugTypeEnum" 인터페이스 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 메서드가 특정 인터페이스 식별자에 대한 정보를 검색하지 못하면 "ICorDebugTypeEnum" 컬렉션의 해당 `ELEMENT_TYPE_END` 항목에는 데이터 검색 문제 또는 `ELEMENT_TYPE_VOID` 알 수 없는 인터페이스 식별자로 인한 오류 유형이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 윈도우 런타임  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugAppDomain3 인터페이스](icordebugappdomain3-interface.md)
