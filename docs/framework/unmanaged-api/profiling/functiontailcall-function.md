---
description: '자세히 알아보기: FunctionTailcall 함수'
title: FunctionTailcall 함수
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: aeb6e7dcbf52fc57ebb7b6dca22331c27cadc186
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760030"
---
# <a name="functiontailcall-function"></a>FunctionTailcall 함수

현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출을 수행 하려고 함을 프로파일러에 알립니다.  
  
> [!NOTE]
> `FunctionTailcall`함수는 .NET Framework 버전 2.0에서 더 이상 사용 되지 않습니다. 계속 작동 하지만 성능이 저하 됩니다. 대신 [FunctionTailcall2](functiontailcall2-function.md) 함수를 사용 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>매개 변수

`funcID` 진행 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.

## <a name="remarks"></a>설명  

 마무리 호출의 대상 함수는 현재 스택 프레임을 사용 하며, 마무리 호출을 수행한 함수의 호출자에 게 직접 반환 됩니다. 즉, tail 호출의 대상인 함수에 대해 [Functionleave](functionleave-function.md) 콜백이 실행 되지 않습니다.  
  
 `FunctionTailcall`함수는 콜백입니다. 함수를 구현 해야 합니다. 구현은 `__declspec` ( `naked` ) 저장소 클래스 특성을 사용 해야 합니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.  
  
- 항목에서 FPU (부동 소수점 단위)의 항목을 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 호출자에 의해 푸시되는 모든 매개 변수를 팝 하 여 스택을 복원 해야 합니다.  
  
 의 구현은 `FunctionTailcall` 가비지 수집을 지연 하므로 차단 하면 안 됩니다. 스택이 가비지 컬렉션에 대 한 상태에 있지 않을 수 있기 때문에 구현에서 가비지 수집을 시도 하면 안 됩니다. 가비지 수집을 시도 하면 런타임이 반환 될 때까지 차단 됩니다 `FunctionTailcall` .  
  
 또한 함수는 관리 `FunctionTailcall` 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참조

- [FunctionEnter2 함수](functionenter2-function.md)
- [FunctionLeave2 함수](functionleave2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
