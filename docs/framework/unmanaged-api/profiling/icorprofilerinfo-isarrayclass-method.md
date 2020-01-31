---
title: ICorProfilerInfo::IsArrayClass 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: a6e483d820d183afc8ba6a68fc4635730ffd1e51
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869340"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass 메서드
지정 된 클래스가 배열 클래스 인지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a>매개 변수  
 `classId`  
 진행 검사할 클래스의 ID입니다.  
  
 `pBaseElemType`  
 제한이 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.  
  
 `pBaseClassId`  
 제한이 사용할 수 있는 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.  
  
 `pcRank`  
 제한이 배열의 차수 (차원 수)를 나타내는 정수에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 지정 된 클래스가 배열 클래스인 경우 `IsArrayClass` 메서드는 null이 아닌 모든 출력 매개 변수에 대 한 S_OK HRESULT 및 값을 반환 합니다. 그렇지 않으면 S_FALSE을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
