---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041173"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a>ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드
메타 데이터 토큰 및 지정된 된 함수에 대 한 토큰을 기준으로 사용할 수 있는 메타 데이터 인터페이스 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 [in] 메타 데이터 토큰 및 메타 데이터 인터페이스를 가져올 함수의 ID입니다.  
  
 `riid`  
 [in] 인스턴스를 가져올 메타 데이터 인터페이스의 참조 ID입니다.  
  
 `ppImport`  
 [out] 지정된 된 함수에 대 한 토큰을 기준으로 사용할 수 있는 메타 데이터 인터페이스 인스턴스 주소에 대 한 포인터입니다.  
  
 `pToken`  
 [out] 지정된 된 함수에 대 한 메타 데이터 토큰에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
