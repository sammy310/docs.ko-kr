---
title: ICorProfilerInfo3::GetFunctionTailcall3Info 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
ms.openlocfilehash: 5346792cb2a1309268cb4ba48625aa559777fbaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176996"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a>ICorProfilerInfo3::GetFunctionTailcall3Info 메서드
[FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) 함수에 의해 프로파일러에 보고되는 함수의 스택 프레임을 제공합니다. 이 함수는 `FunctionTailcall3WithInfo` 콜백 중에만 호출할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFunctionTailcall3Info(
            [in]  FunctionID functionId,
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 【인】 반환하는 `FunctionID` 함수의 입니다.  
  
 `eltInfo`  
 [in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다. 프로파일러는 `FunctionTailcall3WithInfo` 함수에 의해 `eltInfo` 프로파일러에 제공된 것과 동일한 것을 제공해야 합니다.  
  
 `pFrameInfo`  
 [out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다. 이 핸들은 프로파일러가 `GetFunctionTailcall3Info` 메서드를 호출한 `FunctionTailcall3WithInfo` 콜백 중에만 유효합니다.  
  
## <a name="remarks"></a>설명  
  
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
