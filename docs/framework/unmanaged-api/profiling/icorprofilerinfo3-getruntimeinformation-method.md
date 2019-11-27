---
title: ICorProfilerInfo3::GetRuntimeInformation 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: 20556d85655a0a1bbe069a94b99c19c774a13ce6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449688"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>ICorProfilerInfo3::GetRuntimeInformation 메서드
프로 파일링 되 고 있는 CLR (공용 언어 런타임)에 대 한 버전 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pClrInstanceId`  
 제한이 프로세스에서 실행 중인 CLR 인스턴스의 담당자 ID입니다. 이는 ETW (Windows 용 이벤트 추적) 시작 이벤트에서 보고 하는 `ClrInstanceID`와 동일 합니다.  
  
 `pRuntimeType`  
 제한이 런타임 형식입니다. 이 매개 변수는 Silverlight의 데스크톱 버전에 대 한 `COR_PRF_DESKTOP_CLR` 또는 Silverlight에서 사용 되는 CLR의 핵심 버전에 대 한 `COR_PRF_CORE_CLR`을 반환 합니다.  
  
 `pMajorVersion`  
 제한이 CLR의 주 버전 번호입니다.  
  
 `pMinorVersion`  
 제한이 CLR의 부 버전 번호입니다.  
  
 `pBuildVersion`  
 제한이 CLR의 빌드 버전 번호입니다.  
  
 `pQFEVersion`  
 제한이 소프트웨어 업데이트와 연결 된 CLR의 버전 번호입니다.  
  
 `cchVersionString`  
 진행 `szVersionString`가 가리키는 버퍼의 길이 (문자 수)입니다.  
  
 `pcchVersionString`  
 제한이 `szVersionString`의 길이 (문자)입니다.  
  
 `szVersionString`  
 제한이 CLR 버전 문자열입니다.  
  
## <a name="remarks"></a>주의  
 모든 매개 변수에 대해 null을 전달할 수 있습니다. 그러나 `szVersionString`가 null이 아닌 경우에는 `pcchVersionString` null 일 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
