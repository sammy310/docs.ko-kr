---
description: '자세히 알아보기: ICorProfilerInfo7:: Getinmemory기호 Slength 메서드'
title: 'ICorProfilerInfo7:: Getinmemory기호 Slength 메서드'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 5d96b17e8abbd023f2d050eff3f121a871a94754
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737118"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a>ICorProfilerInfo7:: Getinmemory기호 Slength 메서드

[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 기호 스트림의 길이를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.  
  
 Pcount기호 바이트  
 제한이 `DWORD` 메서드가 반환 될 때 스트림의 길이 (바이트)를 포함 하는 값에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 `S_OK`메모리 스트림의 길이가 0 인 경우에도이 메서드는를 반환 합니다.  
  
 메서드는를 `CORPROF_E_MODULE_IS_DYNAMIC` 사용 하 여 메서드를 만든 경우를 반환 합니다 <xref:System.Reflection.Emit?displayProperty=nameWithType> .  
  
## <a name="remarks"></a>설명  

 모듈에 메모리 내 기호가 있으면 스트림의 길이가에 배치 됩니다 `pCountSymbolBytes` . 모듈에 메모리 내 `*pCountSymbolBytes = 0` 기호 ()가 없는 경우  
  
> [!NOTE]
> 현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다. 리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는를 반환 합니다 `CORPROF_E_MODULE_IS_DYNAMIC` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo7 인터페이스](icorprofilerinfo7-interface.md)
