---
description: '자세히 알아보기: ICorDebugAppDomain3:: GetCachedWinRTTypes 메서드'
title: ICorDebugAppDomain3::GetCachedWinRTTypes 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: 813fb6c05d5e1e5f119424c6e983b86b3ff5889d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772239"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypes 메서드

모든 캐시 된 Windows 런타임 형식에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppGuidToTypeEnum`  
 제한이 응용 프로그램 도메인에 현재 로드 된 Windows 런타임 형식의 관리 되는 표현을 열거할 수 있는 [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface 개체에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** Windows 런타임  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugAppDomain3 인터페이스](icordebugappdomain3-interface.md)
