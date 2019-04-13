---
title: ICorDebugMergedAssemblyRecord::GetPublicKey 메서드
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610e46d5cb550a266c5558c49239d1818c1e85de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107278"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a>ICorDebugMergedAssemblyRecord::GetPublicKey 메서드
어셈블리의 공개 키를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbPublicKey`  
 [in] `pbPublicKey` 배열의 최대 바이트 수입니다.  
  
 `pcbPublicKey`  
 [out] `pbPublicKey` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.  
  
 `pbPublicKey`  
 [out] 어셈블리의 공개 키를 포함하는 바이트 배열에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebugMergedAssemblyRecord 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
