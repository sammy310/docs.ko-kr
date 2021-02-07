---
description: 'ICorProfilerInfo4:: EnumThreads 메서드에 대해 자세히 알아보세요.'
title: ICorProfilerInfo4::EnumThreads 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
ms.openlocfilehash: d597e68b8765e135d5bdb403dbdb161b7acbaa9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686936"
---
# <a name="icorprofilerinfo4enumthreads-method"></a>ICorProfilerInfo4::EnumThreads 메서드

프로 파일링 된 프로세스에서 모든 관리 되는 스레드의 컬렉션을 순차적으로 반복 하는 메서드를 제공 하는 열거자를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppEnum`  
 제한이 [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerThreadEnum 인터페이스](icorprofilerthreadenum-interface.md)
- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
