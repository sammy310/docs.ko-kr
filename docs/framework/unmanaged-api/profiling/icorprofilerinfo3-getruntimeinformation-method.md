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
Provides version information about the common language runtime (CLR) that is being profiled.  
  
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
 [out] The representative ID of a running CLR instance in a process. This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.  
  
 `pRuntimeType`  
 [out] The runtime type. This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.  
  
 `pMajorVersion`  
 [out] The major version number of the CLR.  
  
 `pMinorVersion`  
 [out] The minor version number of the CLR.  
  
 `pBuildVersion`  
 [out] The build version number of the CLR.  
  
 `pQFEVersion`  
 [out] The version number of the CLR that is associated with a software update.  
  
 `cchVersionString`  
 [in] The length, in characters, of the buffer that `szVersionString` points to.  
  
 `pcchVersionString`  
 [out] The length, in characters, of `szVersionString`.  
  
 `szVersionString`  
 [out] The CLR version string.  
  
## <a name="remarks"></a>주의  
 You may pass null for any parameter. However, `pcchVersionString` cannot be null unless `szVersionString` is also null.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
