---
title: ICorDebugAppDomainEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fefc933cc84fede1f3dea16d4b13e09801a96e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497355"
---
# <a name="icordebugappdomainenumnext-method"></a>ICorDebugAppDomainEnum::Next 메서드
현재 커서 위치부터 컬렉션에서 지정 된 응용 프로그램 도메인 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 검색할 응용 프로그램 도메인의 수입니다.  
  
 `values`  
 [out] 포인터의 배열에는 각 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체를 가리킵니다.  
  
 `pceltFetched`  
 [out] 실제로 반환 된 응용 프로그램 도메인 수에 대 한 포인터입니다. 이 값은 null 일 수 있으면 `celt` 하나입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
