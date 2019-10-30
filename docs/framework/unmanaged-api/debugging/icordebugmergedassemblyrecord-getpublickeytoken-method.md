---
title: 'ICorDebugMergedAssemblyRecord:: GetPublicKeyToken 메서드'
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: 95ed1303b33b328d1f14ecea6cc318e14991cd54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129783"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a>ICorDebugMergedAssemblyRecord:: GetPublicKeyToken 메서드
어셈블리의 공개 키 토큰을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cbPublicKeyToken`  
 [in] `pbPublicKeyToken` 배열의 최대 바이트 수입니다.  
  
 `pcbPublicKeyToken`  
 [out] `pbPublicKeyToken` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.  
  
 `pbPublicKeyToken`  
 [out] 어셈블리의 공개 키 토큰을 포함하는 바이트 배열에 대한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 어셈블리의 공개 키 토큰은 공개 키에 대한 SHA1 해시의 마지막 8바이트입니다.  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugMergedAssemblyRecord 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
