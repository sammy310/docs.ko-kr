---
description: '자세히 알아보기: ICorProfilerCallback:: JITFunctionPitched 메서드'
title: ICorProfilerCallback::JITFunctionPitched 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 11729de2188fe2f2cec7ec16ff7a5d1928cbd75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705722"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>ICorProfilerCallback::JITFunctionPitched 메서드

JIT (just-in-time) 컴파일 된 함수가 메모리에서 제거 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>매개 변수  

 `functionId`  
 진행 제거 된 함수의 ID입니다.  
  
## <a name="remarks"></a>설명  

 제거 된 함수가 호출 되 면 프로파일러는 함수가 다시 컴파일될 때 새 JIT 컴파일 이벤트를 수신 합니다. 현재 CLR (공용 언어 런타임) JIT 컴파일러는 메모리에서 함수를 제거 하지 않으므로이 콜백은 현재 사용 되지 않으며 프로파일러에서 수신 되지 않습니다.  
  
 함수를 다시 `functionId` 컴파일할 때까지 값이 유효 하지 않습니다. 함수가 다시 컴파일되면 동일한 `functionId` 값이 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
