---
title: ICorDebugModuleDebugEvent::GetModule Method
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709507"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>ICorDebugModuleDebugEvent::GetModule Method

방금 로드 또는 언로드된 병합된 모듈을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppModule`  
 [out] 방금 로드 또는 언로드된 병합된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 [Geteventkind](icordebugdebugevent-geteventkind-method.md) 메서드를 호출 하 여 모듈이 로드 또는 언로드 되었는지 여부를 확인할 수 있습니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugModuleDebugEvent 인터페이스](icordebugmoduledebugevent-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
