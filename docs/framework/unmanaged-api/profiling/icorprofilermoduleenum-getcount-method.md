---
title: ICorProfilerModuleEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 190d6477e0474a7f865f231dbf116e845a403a34
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471188"
---
# <a name="icorprofilermoduleenumgetcount-method"></a>ICorProfilerModuleEnum::GetCount 메서드
응용 프로그램에 로드된 관리되는 모듈 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a>매개 변수  
 `celt`  
 [out] 컬렉션에서 런타임 모듈 수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICorProfilerModuleEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
