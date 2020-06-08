---
title: ICorProfilerInfo2::GetStaticFieldInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: e1dd6addd9053ffb6cf2ce23408673d8fca17cb5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496843"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo 메서드
지정 된 필드에 적용 되는 정적의 종류를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>매개 변수  
 `classId`  
 진행 정적 필드가 정의 된 클래스의 ID입니다.  
  
 `fieldToken`  
 진행 정적 필드에 대 한 메타 데이터 토큰입니다.  
  
 `pFieldInfo`  
 제한이 지정 된 필드가 정적 인지 여부를 나타내는 [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) 열거형 값에 대 한 포인터이 고, 그렇지 않으면 필드에 적용 되는 정적의 종류입니다.  
  
## <a name="remarks"></a>설명  
 이 정보는 정적 필드의 주소를 가져오기 위해 호출할 함수를 결정 하는 데 사용할 수 있습니다.  
  
 프로파일러 코드는 여전히 정적 필드에 대 한 메타 데이터를 확인 하 여 실제로 주소가 있는지 확인 해야 합니다. 정적 리터럴 (즉, 상수)은 메타 데이터에만 존재 하 고 주소는 포함 하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](icorprofilerinfo2-interface.md)
