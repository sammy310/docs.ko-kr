---
description: '자세히 알아보기: ICorDebugDataTarget3 인터페이스'
title: ICorDebugDataTarget3 인터페이스
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: fa786b920d1a2e72dc2a7918e0514773862a0e85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710441"
---
# <a name="icordebugdatatarget3-interface"></a>ICorDebugDataTarget3 인터페이스

[ICorDebugDataTarget](icordebugdatatarget-interface.md) 인터페이스를 논리적으로 확장 하 여 로드 된 모듈에 대 한 정보를 제공 합니다.  
  
## <a name="method"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetLoadedModules 메서드](icordebugdatatarget3-getloadedmodules-method.md)|지금까지 로드된 모듈 목록을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다. .NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
