---
description: '자세한 정보: Cordebug인터페이스 버전 열거'
title: CorDebugInterfaceVersion 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 35b8fd6eae2b7999d7669632506cfea43dffbd45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801646"
---
# <a name="cordebuginterfaceversion-enumeration"></a>CorDebugInterfaceVersion 열거형

인터페이스, 특정 .NET Framework 버전 또는 인터페이스가 적용된 .NET Framework 버전을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a>구성원  

 다음 테이블에는 각 열거형 값에서 해당 인터페이스의 링크와 인터페이스가 지원되는 첫 번째.NET Framework 버전이 나와 있습니다.  
  
|멤버|설명|.NET Framework 버전|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|.NET Framework 버전이 잘못되었습니다.|-|  
|`CorDebugVersion_1_0`|모든 서비스 팩을 포함한 .NET Framework 버전이 1.0입니다.|1.0|  
|`CorDebugVersion_1_1`|모든 서비스 팩을 포함한 .NET Framework 버전이 1.1입니다.|1.1|  
|`CorDebugVersion_2_0`|모든 서비스 팩을 포함한 .NET Framework 버전이 2.0입니다.|2.0|  
|`CorDebugVersion_4_0`|모든 서비스 팩을 포함한 .NET Framework 버전이 4입니다.|4|  
|`CorDebugVersion_4_5`|모든 서비스 팩을 포함한 .NET Framework 버전이 4.5입니다.|4.5.|  
|`ver_ICorDebugManagedCallback`|[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)|1.0|  
|`ver_ICorDebugUnmanagedCallback`|[ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)|1.0|  
|`ver_ICorDebug`|[ICorDebug](icordebug-interface.md)|1.0|  
|`ver_ICorDebugController`|[ICorDebugController](icordebugcontroller-interface.md)|1.0|  
|`ver_ICorDebugAppDomain`|[ICorDebugAppDomain](icordebugappdomain-interface.md)|1.0|  
|`ver_ICorDebugAssembly`|[ICorDebugAssembly](icordebugassembly-interface.md)|1.0|  
|`ver_ICorDebugProcess`|[ICorDebugProcess](icordebugprocess-interface.md)|1.0|  
|`ver_ICorDebugBreakpoint`|[ICorDebugBreakpoint](icordebugbreakpoint-interface.md)|1.0|  
|`ver_ICorDebugFunctionBreakpoint`|[ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)|1.0|  
|`ver_ICorDebugModuleBreakpoint`|[ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)|1.0|  
|`ver_ICorDebugValueBreakpoint`|[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)|1.0|  
|`ver_ICorDebugStepper`|[ICorDebugStepper](icordebugstepper-interface.md)|1.0|  
|`ver_ICorDebugRegisterSet`|[ICorDebugRegisterSet](icordebugregisterset-interface.md)|1.0|  
|`ver_ICorDebugThread`|[ICorDebugThread](icordebugthread-interface.md)|1.0|  
|`ver_ICorDebugChain`|[ICorDebugChain](icordebugchain-interface.md)|1.0|  
|`ver_ICorDebugFrame`|[ICorDebugFrame](icordebugframe-interface.md)|1.0|  
|`ver_ICorDebugILFrame`|[ICorDebugILFrame](icordebugilframe-interface.md)|1.0|  
|`ver_ICorDebugNativeFrame`|[ICorDebugNativeFrame](icordebugnativeframe-interface.md)|1.0|  
|`ver_ICorDebugModule`|[ICorDebugModule](icordebugmodule-interface.md)|1.0|  
|`ver_ICorDebugFunction`|[ICorDebugFunction](icordebugfunction-interface1.md)|1.0|  
|`ver_ICorDebugCode`|[ICorDebugCode](icordebugcode-interface1.md)|1.0|  
|`ver_ICorDebugClass`|[ICorDebugClass](icordebugclass-interface.md)|1.0|  
|`ver_ICorDebugEval`|[ICorDebugEval](icordebugeval-interface.md)|1.0|  
|`ver_ICorDebugValue`|[ICorDebugValue](icordebugvalue-interface.md)|1.0|  
|`ver_ICorDebugGenericValue`|[ICorDebugGenericValue](icordebuggenericvalue-interface.md)|1.0|  
|`ver_ICorDebugReferenceValue`|[ICorDebugReferenceValue](icordebugreferencevalue-interface.md)|1.0|  
|`ver_ICorDebugHeapValue`|[ICorDebugHeapValue](icordebugheapvalue-interface.md)|1.0|  
|`ver_ICorDebugObjectValue`|[ICorDebugObjectValue](icordebugobjectvalue-interface.md)|1.0|  
|`ver_ICorDebugBoxValue`|[ICorDebugBoxValue](icordebugboxvalue-interface.md)|1.0|  
|`ver_ICorDebugStringValue`|[ICorDebugStringValue](icordebugstringvalue-interface.md)|1.0|  
|`ver_ICorDebugArrayValue`|[ICorDebugArrayValue](icordebugarrayvalue-interface.md)|1.0|  
|`ver_ICorDebugContext`|[ICorDebugContext](icordebugcontext-interface.md)|1.0|  
|`ver_ICorDebugEnum`|[ICorDebugEnum](icordebugenum-interface1.md)|1.0|  
|`ver_ICorDebugObjectEnum`|[ICorDebugObjectEnum](icordebugobjectenum-interface.md)|1.0|  
|`ver_ICorDebugBreakpointEnum`|[ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)|1.0|  
|`ver_ICorDebugStepperEnum`|[ICorDebugStepperEnum](icordebugstepperenum-interface.md)|1.0|  
|`ver_ICorDebugProcessEnum`|[ICorDebugProcessEnum](icordebugprocessenum-interface.md)|1.0|  
|`ver_ICorDebugThreadEnum`|[ICorDebugThreadEnum](icordebugthreadenum-interface1.md)|1.0|  
|`ver_ICorDebugFrameEnum`|[ICorDebugFrameEnum](icordebugframeenum-interface.md)|1.0|  
|`ver_ICorDebugChainEnum`|[ICorDebugChainEnum](icordebugchainenum-interface.md)|1.0|  
|`ver_ICorDebugModuleEnum`|[ICorDebugModuleEnum](icordebugmoduleenum-interface.md)|1.0|  
|`ver_ICorDebugValueEnum`|[ICorDebugValueEnum](icordebugvalueenum-interface.md)|1.0|  
|`ver_ICorDebugCodeEnum`|[ICorDebugCodeEnum](icordebugcodeenum-interface.md)|1.0|  
|`ver_ICorDebugTypeEnum`|[ICorDebugTypeEnum](icordebugtypeenum-interface.md)|1.0|  
|`ver_ICorDebugErrorInfoEnum`|[ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)|1.0|  
|`ver_ICorDebugAppDomainEnum`|[ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)|1.0|  
|`ver_ICorDebugAssemblyEnum`|[ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)|1.0|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)|1.0|  
|`ver_ICorDebugEditAndContinueSnapshot`|[ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)|1.0|  
|`ver_ICorDebugManagedCallback2`|[ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)|2.0|  
|`ver_ICorDebugAppDomain2`|[ICorDebugAppDomain2](icordebugappdomain2-interface.md)|2.0|  
|`ver_ICorDebugProcess2`|[ICorDebugProcess2](icordebugprocess2-interface1.md)|2.0|  
|`ver_ICorDebugStepper2`|[ICorDebugStepper2](icordebugstepper2-interface1.md)|2.0|  
|`ver_ICorDebugRegisterSet2`|[ICorDebugRegisterSet2](icordebugregisterset2-interface.md)|2.0|  
|`ver_ICorDebugThread2`|[ICorDebugThread2](icordebugthread2-interface.md)|2.0|  
|`ver_ICorDebugILFrame2`|[ICorDebugILFrame2](icordebugilframe2-interface.md)|2.0|  
|`ver_ICorDebugModule2`|[ICorDebugModule2](icordebugmodule2-interface.md)|2.0|  
|`ver_ICorDebugFunction2`|[ICorDebugFunction2](icordebugfunction2-interface.md)|2.0|  
|`ver_ICorDebugCode2`|[ICorDebugCode2](icordebugcode2-interface.md)|2.0|  
|`ver_ICorDebugClass2`|ICorDebugClass2|2.0|  
|`ver_ICorDebugValue2`|ICorDebugValue2|2.0|  
|`ver_ICorDebugEval2`|"ICorDebugEval2"입니다.|2.0|  
|`ver_ICorDebugObjectValue2`|ICorDebugObjectValue2|2.0|  
|`ver_ICorDebugThread3`|[ICorDebugThread3](icordebugthread3-interface.md)|4|  
|`ver_ICorDebugThread4`|[ICorDebugThread4](icordebugthread4-interface.md)|4|  
|`ver_ICorDebugStackWalk`|[ICorDebugStackWalk](icordebugstackwalk-interface.md)|4|  
|`ver_ICorDebugNativeFrame2`|[ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)|4|  
|`ver_ICorDebugInternalFrame2`|[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)|4|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)|4|  
|`ver_ICorDebugHeapValue3`|[ICorDebugHeapValue3 인터페이스](icordebugheapvalue3-interface.md)|4|  
|`ver_ICorDebugBlockingObjectEnum`|[ICorDebugBlockingObjectEnum 인터페이스](icordebugblockingobjectenum-interface.md)|4|  
|`ver_ICorDebugValue3`|[ICorDebugValue3](icordebugvalue3-interface.md)|4|  
|`ver_ICorDebugComObjectValue`|[ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)|4.5.|  
|`ver_ICorDebugAppDomain3`|[ICorDebugAppDomain3](icordebugappdomain3-interface.md)|4.5.|  
|`ver_ICorDebugCode3`|[ICorDebugCode3](icordebugcode3-interface.md)|4.5.|  
|`ver_ICorDebugILFrame3`|[ICorDebugILFrame3](icordebugilframe3-interface.md)|4.5.|  
|`CorDebugLatestVersion`|모든 서비스 팩을 포함한 .NET Framework 버전이 최신 버전입니다.|-|  
  
## <a name="remarks"></a>설명  

 디버거는 `CorDebugInterfaceVersion` [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) 함수에서 열거형을 사용 하 여 디버거가 지 원하는 .NET Framework의 가장 높은 버전을 지정할 수 있습니다.  
  
## <a name="interface-names"></a>인터페이스 이름  

 디버깅 API에서 인터페이스 이름 끝에 표시되는 숫자(예: `ICorDebugThread3`의 경우 "3")는 .NET Framework의 버전이 아닌 인터페이스의 버전을 지정합니다. .NET Framework 버전 1에 처음 도입된 인터페이스를 제외하면 디버깅 API의 모든 인터페이스 이름에는 버전 번호가 포함됩니다. 인터페이스 버전 번호와 .NET Framework 버전 번호가 일치하는 경우 단순히 우연적인 일입니다.  
  
- .NET Framework 버전 1.0에 도입된 인터페이스의 경우 모두 암시적으로 버전 1이므로 번호를 포함하지 않습니다.  
  
- .NET Framework 버전 1.1은 버전 1.0 인터페이스를 사용하며 새로운 디버깅 인터페이스는 제공하지 않습니다.  
  
- .NET Framework 버전 2.0에 도입된 14개 디버깅 인터페이스는 버전 1의 해당 인터페이스가 논리적으로 확장된 것이며 이름에 숫자 "2"가 포함됩니다.  
  
- .NET Framework 버전 3.0 및 3.5는 기존 .NET Framework 2.0 인터페이스를 사용하며 새로운 인터페이스는 제공하지 않습니다.  
  
- .NET Framework 4는 인터페이스 버전을 혼합 해 서 소개 합니다. 예를 들어 `ICorDebugThread3` 및 `ICorDebugThread4`는 모두 `ICorDebugThread` 인터페이스의 3번째/4번째 버전으로 표시됩니다. .NET Framework 4에는 인터페이스의 첫 번째 버전과 `ICorDebugStackWalk` 두 번째 버전의 `ICorDebugNativeFrame` 인터페이스 ()도 도입 `ICorDebugNativeFrame2` 되었습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 열거형](debugging-enumerations.md)
