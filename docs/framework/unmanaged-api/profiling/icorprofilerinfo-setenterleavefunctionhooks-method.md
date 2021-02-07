---
description: '자세히 알아보기: ICorProfilerInfo:: SetEnterLeaveFunctionHooks 메서드'
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
ms.openlocfilehash: 45c161a76f3ae568da6a83a2c45acb214a327ff1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687209"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>ICorProfilerInfo::SetEnterLeaveFunctionHooks 메서드

관리 되는 함수의 "enter", "leave" 및 "tailcall" 후크에 대해 호출 될 프로파일러 구현 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pFuncEnter`  
 진행 [Functionenter](functionenter-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.  
  
 `pFuncLeave`  
 진행 [Functionleave](functionleave-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.  
  
 `pFuncTailcall`  
 진행 [FunctionTailcall](functiontailcall-function.md) 콜백으로 사용할 구현에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 .NET Framework 버전 1.0에서는 각 함수 포인터가 null 일 수 있으므로 해당 콜백을 사용 하지 않도록 설정할 수 있습니다.  
  
 한 번에 하나의 콜백 집합만 활성 상태일 수 있습니다. 따라서 프로파일러가 `SetEnterLeaveFunctionHooks` 및 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 모두 호출 하면가 우선적으로 `SetEnterLeaveFunctionHooks2` 적용 됩니다.  
  
 `SetEnterLeaveFunctionHooks`메서드는 프로파일러의 [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서만 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
