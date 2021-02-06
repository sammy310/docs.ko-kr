---
description: '자세히 알아보기: ICorProfilerInfo3:: GetModuleInfo2 메서드'
title: ICorProfilerInfo3::GetModuleInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
ms.openlocfilehash: 94a1159db9388e23fe244788dca0b2cf557c6cae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646740"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a>ICorProfilerInfo3::GetModuleInfo2 메서드

모듈 ID가 지정된 경우 모듈의 파일 이름, 모듈의 부모 어셈블리 ID 및 모듈 속성을 설명하는 비트 마스크를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 [in] 정보가 검색되는 모듈의 ID입니다.  
  
 `ppBaseLoadAddress`  
 [out] 모듈이 로드되는 기본 주소입니다.  
  
 `cchName`  
 [in] `szName` 반환 버퍼의 길이(문자)입니다.  
  
 `pcchName`  
 [out] 반환되는 모듈 파일 이름의 총 문자 길이에 대한 포인터입니다.  
  
 `szName`  
 [out] 호출자가 제공한 와이드 문자 버퍼입니다. 메서드가 반환되면 이 버퍼에 모듈의 파일 이름이 포함됩니다.  
  
 `pAssemblyId`  
 [out] 모듈의 부모 어셈블리 ID에 대한 포인터입니다.  
  
 `pdwModuleFlags`  
 제한이 모듈의 속성을 지정 하는 [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) 열거형의 값에 대 한 비트 마스크입니다.  
  
## <a name="remarks"></a>설명  

 동적 모듈의 경우 `szName` 매개 변수는 모듈의 메타데이터 이름이고 기본 주소는 0입니다. 메타데이터 이름은 메타데이터 내부에서 Module 테이블의 Name 열에 있는 값입니다. 이는 <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> 관리 코드에 속성으로 노출 되 고, `szName` 관리 되지 않는 메타 데이터 클라이언트 코드에 대 한 [IMetaDataImport:: GetScopeProps](../metadata/imetadataimport-getscopeprops-method.md) 메서드의 매개 변수로도 노출 됩니다.  
  
 `GetModuleInfo2`모듈 id가 존재 하는 즉시 메서드를 호출할 수 있지만, 프로파일러가 [ICorProfilerCallback:: ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) 콜백을 받을 때까지 부모 어셈블리의 id를 사용할 수 없습니다.  
  
 `GetModuleInfo2`가 반환된 후 `szName` 버퍼가 모듈의 전체 파일 이름을 포함하기에 충분히 큰지 확인해야 합니다. 이렇게 하려면 `pcchName`가 가리키는 값을 `cchName` 매개 변수의 값과 비교합니다. `pcchName`이 `cchName`보다 큰 값을 가리키는 경우 더 큰 `szName` 버퍼를 할당하고 `cchName`을 더 큰 새 크기로 업데이트한 후 `GetModuleInfo2`를 다시 호출합니다.  
  
 또는 길이가 0인 `szName` 버퍼로 `GetModuleInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다. 그런 다음 버퍼 크기를 `pcchName`에 반환된 값으로 설정하고 `GetModuleInfo2`을 다시 호출합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
