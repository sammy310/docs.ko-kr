---
title: ICorDebugAssembly2::IsFullyTrusted 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd3b977a894f8cb1fc9a866f5a43265d917db513
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494443"
---
# <a name="icordebugassembly2isfullytrusted-method"></a>ICorDebugAssembly2::IsFullyTrusted 메서드
여부를 어셈블리에 부여 된 완전 신뢰 런타임 보안 시스템에서 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbFullyTrusted`  
 [out] `true` 어셈블리에 권한이 부여 된 경우 완전 신뢰 런타임 보안 시스템에서이 고, 그렇지 `false`합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 HRESULT의 CORDBG_E_NOTREADY 어셈블리에 대 한 보안 정책을 아직 해결 즉, 어셈블리의 코드가 없으면 경우 아직 실행을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
