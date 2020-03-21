---
title: ICorProfilerInfo3::GetFunctionEnter3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 50d16b8036144d6ede349149fa4ae37344064d8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177022"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info 메서드
[FunctionEnter3WithInfo](functionenter3withinfo-function.md) 함수에 의해 프로파일러에 보고되는 함수의 스택 프레임 및 인수 정보를 제공합니다. 이 함수는 `FunctionEnter3WithInfo` 콜백 중에만 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 입력 중인 함수의 `FunctionID`입니다.  
  
 `eltInfo`  
 [in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다. 프로파일러는 `eltInfo` [FunctionEnter3WithInfo](functionenter3withinfo-function.md) 함수에 의해 주어진 것과 동일한 것을 제공해야 합니다.  
  
 `pFrameInfo`  
 [out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다. 이 핸들은 프로파일러가 `GetFunctionEnter3Info` 메서드를 호출한 `FunctionEnter3WithInfo` 콜백 중에만 유효합니다.  
  
 `pcbArgumentInfo`  
 【인, 아웃】 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조의 총 크기에 대한 포인터(가리키는 인수 범위에 대한 추가 [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) `pArgumentInfo`구조)입니다. 지정된 크기가 충분하지 않으면 ERROR_INSUFFICIENT_BUFFER가 반환되고 예상 크기가 `pcbArgumentInfo`에 저장됩니다. 단순히 `*pcbArgumentInfo`의 예상 값을 검색하기 위해 `GetFunctionEnter3Info`를 호출하려면 `*pcbArgumentInfo`=0 및 `pArgumentInfo`=NULL을 설정합니다.  
  
 `pArgumentInfo`  
 【아웃】 메모리에서 함수 인수의 위치를 왼쪽에서 오른쪽 순서로 설명하는 [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) 구조에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 프로파일러는 검사되는 함수의 `COR_PRF_FUNCTION_ARGUMENT_INFO` 구조체에 대해 충분한 공간을 할당해야 하며 `pcbArgumentInfo` 매개 변수에 크기를 나타내야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [함수엔터3정보](functionenter3withinfo-function.md)
- [함수리브3정보정보](functionleave3withinfo-function.md)
- [함수테일콜3정보정보](functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3 인터페이스](icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
