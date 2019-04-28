---
title: FunctionEnter 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6018b5b06a138b38b7b97df280a3e4c4ea0512d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598963"
---
# <a name="functionenter-function"></a>FunctionEnter 함수
컨트롤이 함수에 전달 되 고 있음을 프로파일러에 알립니다.  
  
> [!NOTE]
>  `FunctionEnter` 함수는.NET Framework 버전 2.0에서에서 사용 되지 않습니다 및 용도는 성능 저하가 발생 합니다. 사용 된 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 함수를 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `funcID`  
 [in] 컨트롤이 전달 함수의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 `FunctionEnter` 함수 콜백을 구현 해야 합니다. 구현을 사용 해야 합니다 `__declspec`(`naked`) 저장소 클래스 특성입니다.  
  
 실행 엔진은이 함수를 호출 하기 전에 모든 레지스터를 저장 하지 않습니다.  
  
- 항목에는 부동 소수점 FPU (단위)에 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.  
  
- 종료 시 스택의 호출자에 의해 푸시된 모든 매개 변수에 팝 하 여 복원 해야 합니다.  
  
 구현의 `FunctionEnter` 가비지 수집 지연 될 수 있으므로 차단 하지 않아야 합니다. 구현 해야 스택의 가비지 컬렉션에 게 친숙 한 상태의 수 없을 수도 가비지 수집을 시도 하지 않습니다. 런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionEnter` 반환 합니다.  
  
 또한는 `FunctionEnter` 함수를 호출 해서는 안 관리 코드로 또는는 관리 되는 메모리를 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고자료

- [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [프로파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
