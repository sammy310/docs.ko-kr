---
description: '자세히 알아보기: ICorProfilerInfo:: GetILFunctionBodyAllocator 메서드'
title: ICorProfilerInfo::GetILFunctionBodyAllocator 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 25d059d784fe64231d4d2ff3d23b4820443873cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647429"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a>ICorProfilerInfo::GetILFunctionBodyAllocator 메서드

MSIL (Microsoft 중간 언어) 코드에서 메서드의 본문을 교환 하는 데 사용할 메모리를 할당 하는 메서드를 제공 하는 인터페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 진행 메서드가 있는 모듈의 ID입니다.  
  
 `ppMalloc`  
 제한이 메모리를 할당 하는 메서드를 제공 하는 [Imethodmalloc](imethodmalloc-interface.md) 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 MSIL 코드의 메서드 본문은 로드 된 모듈을 기준으로 하는 RVA (상대 가상 주소)로 배치 되어야 합니다. 즉, 4gb 내에서 모듈을 따릅니다. 도구를 사용 하 여 메서드의 본문을 쉽게 교환할 수 있도록 `GetILFunctionBodyAllocator` 메서드는 해당 범위 내에서 메모리가 할당 되도록 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
