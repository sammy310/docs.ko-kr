---
title: ICorDebugFunction 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550b85474c1ccd7e125549e86df906439caf410e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621494"
---
# <a name="icordebugfunction-interface"></a>ICorDebugFunction 인터페이스

관리되는 함수 또는 메서드를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|이 함수의 시작 부분에 중단점을 만듭니다.|  
|[GetClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.|  
|[GetCurrentVersionNumber 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|이 함수에 대 한 최신 편집의 버전 번호를 가져옵니다.|  
|[GetILCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|이 함수에 대 한 Microsoft의 MSIL (intermediate language) 코드를 가져옵니다.|  
|[GetLocalVarSigToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|이 표시 되는 함수의 로컬 변수 서명에 대 한 메타 데이터 토큰을 가져옵니다 `ICorDebugFunction` 인스턴스.|  
|[GetModule 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|이 함수는 정의 된 모듈을 가져옵니다.|  
|[GetNativeCode 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|이 함수에 대 한 네이티브 코드를 가져옵니다.|  
|[GetToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|이 함수에 대 한 메타 데이터를 토큰을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugFunction` 인터페이스는 제네릭 형식 매개 변수를 사용 하 여 함수를 나타내지 않습니다. 예를 들어를 `ICorDebugFunction` 인스턴스는 나타냅니다 `Func<T>` 있지만 `Func<string>`합니다. 호출 [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) 제네릭 형식 매개 변수를 가져오려고 합니다.  
  
 메서드의 메타 데이터 토큰 간의 관계 `mdMethodDef`, 및 메서드의 `ICorDebugFunction` 개체가 함수에서 편집 하며 계속 하기는 허용 하는 여부에 따라 달라 집니다.  
  
- 사이 한 일 관계가 있습니다 편집 하며 계속 하기 함수에 대해 허용 되지 않는 경우는 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다. 즉, 함수에 하나 `ICorDebugFunction` 개체와 `mdMethodDef` 토큰입니다.  
  
- 사이 다 대 일 관계가 편집 하며 계속 하기는 함수에 대해 허용 되 면 합니다 `ICorDebugFunction` 개체 및 `mdMethodDef` 토큰입니다. 즉, 함수가 대부분의 있을 `ICorDebugFunction`, 함수의 각 버전에 대 한 있지만 하나만 `mdMethodDef` 토큰입니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:**  CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
