---
title: ICorProfilerInfo4::GetCodeInfo3 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: 54e522aaaf23ae81b96b6be7168a9a13f28a16d2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496141"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a>ICorProfilerInfo4::GetCodeInfo3 메서드
지정된 함수의 JIT 다시 컴파일된 버전과 연결된 네이티브 코드의 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionID`  
 [in] 네이티브 코드가 연결된 함수의 ID입니다.  
  
 `reJitId`  
 [in] JIT 다시 컴파일된 함수의 ID입니다.  
  
 `cCodeInfos`  
 [in] `codeInfos` 배열의 크기입니다.  
  
 `pcCodeInfos`  
 제한이 사용할 수 있는 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 총 수에 대 한 포인터입니다.  
  
 `codeInfos`  
 [out] 호출자가 제공한 버퍼입니다. 메서드가 반환된 후에는 각각 네이티브 코드 블록을 설명하는 `COR_PRF_CODE_INFO` 구조체의 배열을 포함합니다.  
  
## <a name="remarks"></a>설명  
 `GetCodeInfo3`메서드는 지정 된 IP 주소를 포함 하는 함수의 JIT 다시 컴파일된 ID를 [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)는 점을 제외 하 고는와 유사 합니다.  
  
> [!NOTE]
> `GetCodeInfo3`는 가비지 수집을 트리거할 수 있지만 [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) 는 그렇지 않습니다. 자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT를 참조 하세요.  
  
 범위는 CIL(Common Intermediate Language) 오프셋의 오름차순으로 정렬됩니다.  
  
 `GetCodeInfo3`가 반환 된 후 `codeInfos` 버퍼가 모든 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조를 포함할 수 있을 만큼 충분히 큰지 확인 해야 합니다. 이렇게 하려면 `cCodeInfos` 값을 `cchName` 매개 변수의 값과 비교합니다. `cCodeInfos` [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조의 크기로 나눈 값이 보다 작으면 `pcCodeInfos` 더 큰 버퍼를 할당 하 고를 `codeInfos` `cCodeInfos` 더 큰 새 크기로 업데이트 한 다음를 `GetCodeInfo3` 다시 호출 합니다.  
  
 또는 길이가 0인 `codeInfos` 버퍼로 `GetCodeInfo3`를 먼저 호출하여 올바른 버퍼 크기를 구합니다. 그런 다음 `codeInfos` 버퍼 크기를에서 반환 된 값으로 설정 하 `pcCodeInfos` 고 [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) 구조체의 크기를 곱한 다음를 다시 호출할 수 있습니다 `GetCodeInfo3` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetCodeInfo2 메서드](icorprofilerinfo2-getcodeinfo2-method.md)
- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
