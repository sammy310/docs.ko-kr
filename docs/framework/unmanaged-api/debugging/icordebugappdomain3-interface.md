---
title: ICorDebugAppDomain3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922293"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3 인터페이스
관리 되는 표현에 대 한 정보를 검색 하는 메서드를 제공 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 현재 응용 프로그램 도메인에 로드 된 형식입니다. 이 인터페이스는 ICorDebugAppDomain 및 ICorDebugAppDomain2 인터페이스의 확장입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|모든 캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식입니다.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식은 응용 프로그램 도메인에서 해당 인터페이스 식별자 기반으로 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 디버거에서 함수 평가 호출을 함께 사용할 하려는 `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`합니다. 메서드를 지 원하는 인터페이스 식별자를 검색 하는 경우는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 서버 개체를 디버거가이 인터페이스에서 정의 된 메서드를 사용 하 여 이러한 인터페이스에 해당 하는 관리 되는 형식에 매핑할 수 있습니다.  
  
 이 인터페이스의 인스턴스를 검색 하려면 `QueryInterface` ICorDebugAppDomain 또는 ICorDebugAppDomain2 인터페이스 인스턴스에서 합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
