---
title: ICorProfilerInfo::GetModuleMetaData 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 6e787de6287dc5b3091d3671d3da2f2154b12e88
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869926"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData 메서드
지정 된 모듈에 매핑되는 메타 데이터 인터페이스 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleId`  
 진행 인터페이스 인스턴스가 매핑될 모듈의 ID입니다.  
  
 `dwOpenFlags`  
 진행 매니페스트 파일을 여는 모드를 지정 하는 [Coropenflags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열거형의 값입니다. `ofRead`, `ofWrite` 및 `ofNoTransform` 비트만 유효 합니다.  
  
 `riid`  
 진행 해당 인스턴스를 검색할 메타 데이터 인터페이스의 참조 ID (GUID)입니다. 인터페이스 목록은 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) 를 참조 하세요.  
  
 `ppOut`  
 제한이 메타 데이터 인터페이스 인스턴스의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 메타 데이터를 읽기/쓰기 모드에서 열도록 요청할 수도 있지만이 경우 메타 데이터에 대 한 변경 내용이 컴파일러에서와 같이 최적화 되지 않으므로 프로그램의 메타 데이터 실행 속도가 느려집니다.  
  
 일부 모듈 (예: 리소스 모듈)에는 메타 데이터가 없습니다. 이러한 경우 `GetModuleMetaData`는 HRESULT 값 S_FALSE을 반환 하 고 *`ppOut`에 null을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
