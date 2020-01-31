---
title: ICorDebugDataTarget2::GetImageLocation 메서드
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: ba1cc8c91c53547c6ed4025ee67a69e253f3596d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783575"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>ICorDebugDataTarget2::GetImageLocation 메서드
모듈의 경로를 모듈의 기준 주소에서 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `baseAddress`  
 진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 값입니다.  
  
 `cchName`  
 [in] 모듈 경로를 수신할 버퍼의 문자 수입니다.  
  
 `pcchName`  
 [out] `szName` 버퍼에 기록된 문자 수에 대한 포인터입니다.  
  
 `szName`  
 [out] 모듈의 경로입니다.  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
> 이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugDataTarget2 인터페이스](icordebugdatatarget2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
