---
title: ICorProfilerInfo::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 376b9fc637993f00722c48db7f51650e0a22d931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720921"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a>ICorProfilerInfo::SetILFunctionBody 메서드

지정 된 모듈에 있는 지정 된 함수의 본문을 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 진행 함수가 상주 하는 모듈의 ID입니다.  
  
 `methodid`  
 진행 본문을 바꿀 함수의 토큰입니다.  
  
 `pbNewILMethodHeader`  
 진행 함수의 새 헤더입니다.  
  
## <a name="remarks"></a>설명  

 `SetILFunctionBody`메서드는 메타 데이터에 있는 함수의 상대 가상 주소를 대체 하 여 새 함수 본문을 가리키고 필요한 경우 내부 데이터 구조를 조정 합니다.  
  
 `SetILFunctionBody`JIT (just-in-time) 컴파일러에서 컴파일되지 않은 함수 에서만 메서드를 호출할 수 있습니다.  
  
 [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) 메서드를 사용 하 여 버퍼가 호환 되는지 확인 하기 위해 새 메서드에 대 한 공간을 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
