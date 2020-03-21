---
title: FunctionTailcall2 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175189"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 함수
현재 실행 중인 함수가 다른 함수에 대한 테일 호출을 수행하려고 한다는 프로파일러를 지정하고 스택 프레임에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>매개 변수

- `funcId`

  \[in] 꼬리 호출을 하려고 하는 현재 실행 중인 함수의 식별자입니다.

- `clientData`

  \[in] 프로파일러가 [FunctionIDMapper를](functionidmapper-function.md)통해 이전에 지정한 리메드 함수 식별자입니다.
  
- `func`

  \[in] `COR_PRF_FRAME_INFO` 스택 프레임에 대한 정보를 가리키는 값입니다.

  프로파일러는 [이를 ICorProfilerInfo2:GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) 메서드의 실행 엔진으로 다시 전달할 수 있는 불투명 핸들로 처리해야 합니다.

## <a name="remarks"></a>설명  
 tail 호출의 대상 함수는 현재 스택 프레임을 사용하고 tail 호출을 만든 함수의 호출자에게 직접 반환됩니다. 즉, 테일 호출의 대상인 함수에 대해 [FunctionLeave2](functionleave2-function.md) 콜백이 발행되지 않습니다.  
  
 `func` 값이 변경되거나 소멸될 수 `FunctionTailcall2` 있으므로 함수가 반환된 후 매개 변수 값이 유효하지 않습니다.  
  
 함수는 `FunctionTailcall2` 콜백입니다. 구현해야 합니다. 구현은 `__declspec`()`naked`저장소 클래스 특성을 사용해야 합니다.  
  
 실행 엔진은 이 함수를 호출하기 전에 레지스터를 저장하지 않습니다.  
  
- 입력시 부동 점 단위(FPU)를 포함하여 사용하는 모든 레지스터를 저장해야 합니다.  
  
- 종료 시 호출자에 의해 푸시된 모든 매개 변수를 터뜨려 스택을 복원해야 합니다.  
  
 가비지 `FunctionTailcall2` 수집을 지연시킬 수 있으므로 구현이 차단되어서는 안 됩니다. 스택이 가비지 콜렉션 친화적인 상태에 있지 않을 수 있으므로 구현은 가비지 수집을 시도해서는 안 됩니다. 가비지 수집을 시도하면 런타임이 `FunctionTailcall2` 반환될 때까지 차단됩니다.  
  
 또한 함수는 `FunctionTailcall2` 관리 되는 코드에 호출 하거나 어떤 식으로든 관리되는 메모리 할당을 발생 하지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르프로프.아이들  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [FunctionEnter2 함수](functionenter2-function.md)
- [FunctionLeave2 함수](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
