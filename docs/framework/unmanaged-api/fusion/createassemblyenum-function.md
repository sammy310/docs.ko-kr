---
title: CreateAssemblyEnum 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771880"
---
# <a name="createassemblyenum-function"></a>CreateAssemblyEnum 함수
포인터를 가져는 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 지정 된 어셈블리의 개체를 열거할 수 있는 인스턴스 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a>매개 변수  
 `pEnum`  
 [out] 요청 된 요소가 있는 메모리 위치에 대 한 포인터 `IAssemblyEnum` 포인터입니다.  
  
 `pUnkReserved`  
 [in] 향후 확장성을 위해 예약 되어 있습니다. `pUnkReserved` null 참조 여야 합니다.  
  
 `pName`  
 [in] `IAssemblyName` 요청된 된 어셈블리입니다. 이 이름은 열거형 필터링에 사용 됩니다. 전역 어셈블리 캐시의 모든 어셈블리를 열거 하는 null 일 수 있습니다.  
  
 `dwFlags`  
 [in] 열거자의 동작을 수정 하기 위한 플래그입니다. 이 매개 변수에서 정확히 하나의 비트가 포함 된 [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) 열거형입니다.  
  
 `pvReserved`  
 [in] 향후 확장성을 위해 예약 되어 있습니다. `pvReserved` null 참조 여야 합니다.  
  
## <a name="remarks"></a>설명  
 합니다 `dwFlags` 매개 변수에서 정확히 하나의 비트가 포함 된 `ASM_CACHE_FLAGS` 열거형입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IAssemblyEnum 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
