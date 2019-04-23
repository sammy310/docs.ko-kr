---
title: CorDebugCodeInvokeKind 열거형
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3b4906f988d09f7b01aee40e8f63b589da5f33d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086418"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>CorDebugCodeInvokeKind 열거형
내보낸 함수가 관리 코드를 호출하는 방법을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|이 메서드가 관리 코드를 호출하는 경우 나중에 명시적 이벤트 또는 중단점을 사용하여 해당 코드를 찾아야 합니다.<br /><br /> -- 또는 --<br /><br /> 이 메서드를 쉽게 중지할 수 있는 방법이 없어 해당 메서드가 호출하는 일부 관리 코드가 누락될 수 있습니다.<br /><br /> -- 또는 --<br /><br /> 메서드가 관리 코드를 호출하지 않을 수도 있습니다.|  
|`CODE_INVOKE_KIND_RETURN`|이 메서드는 반환 명령을 통해 관리 코드를 호출합니다. 단계별 실행 시 다음 관리 코드에 도달하게 됩니다.|  
|`CODE_INVOKE_KIND_TAILCALL`|이 메서드는 마무리 호출을 통해 관리 코드를 호출합니다. 호출 명령을 한 단계씩/프로시저 단위로 실행하면 관리 코드에 도달하게 됩니다.|  
  
## <a name="remarks"></a>설명  
 이 열거형은에서 사용 된 [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) 관리 되는 코드를 한 단계씩 실행 하는 방법에 대 한 정보를 제공 하는 방법입니다.  
  
> [!NOTE]
>  이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
