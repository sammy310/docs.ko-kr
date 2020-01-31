---
title: ICorProfilerCallback::ExceptionCLRCatcherFound 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866494"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a>ICorProfilerCallback::ExceptionCLRCatcherFound 메서드
예외에 대 한 `catch` 블록을 CLR (공용 언어 런타임) 내에서 찾을 때 호출 됩니다. 이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.0  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ExceptionCLRCatcherExecute 메서드](icorprofilercallback-exceptionclrcatcherexecute-method.md)
