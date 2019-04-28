---
title: ICorDebugHeapValue::IsValid 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e1edb1d25a62a9a689c397339740e563d986c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700221"
---
# <a name="icordebugheapvalueisvalid-method"></a>ICorDebugHeapValue::IsValid 메서드
이 ICorDebugHeapValue이 나타내는 개체가 올바른지 여부를 나타내는 값을 가져옵니다.  
  
 이 메서드는.NET Framework 버전 2.0에서에서 더 이상 사용 되지 되었습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbValid`  
 [out] 힙에서이 값이 유효한 지 여부를 나타내는 부울 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 값을 가비지 수집기에서 회수 된 경우에 올바르지 않습니다.  
  
 이 메서드는 사용되지 않습니다. .NET Framework 2.0에서는 모든 값이 될 때까지 유효 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 이때 값은 유효성을 검사 하지 않습니다.에서 호출 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
