---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO 구조
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 861b31e5621e9a7b40403d249c6a5c8c4ac25db8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501042"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>COR_PRF_ASSEMBLY_REFERENCE_INFO 구조
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 어셈블리 참조에 대한 정보를 공용 언어 런타임에 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|어셈블리의 공개 키 또는 토큰에 대한 포인터입니다.|  
|`cbPublicKeyOrToken`|공개 키 또는 토큰의 바이트 수입니다.|  
|`szName`|참조되는 어셈블리의 이름입니다.|  
|`pMetaData`|어셈블리의 메타데이터에 대한 포인터입니다.|  
|`pbHashValue`|해시 BLOB(Binary Large Object)에 대한 포인터입니다.|  
|`cbHashValue`|해시 BLOB의 바이트 수입니다.|  
|`dwAssemblyRefFlags`|어셈블리의 플래그입니다.|  
  
## <a name="remarks"></a>설명  
 프로파일러는 어셈블리 참조 closure 워커를 수행할 때 공용 언어 런타임이 고려해야 하는 추가 어셈블리 참조를 선언할 때 `COR_PRF_EX_CLAUSE_INFO` 구조체를 채웁니다.  
  
 프로파일러가 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드에 등록 하는 경우 런타임은 로드 될 어셈블리의 경로 및 이름과 해당 메서드에 대 한 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스 개체에 대 한 포인터를 전달 합니다. 그런 다음 프로파일러는 [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) `COR_PRF_ASSEMBLY_REFERENCE_INFO` [ICorProfilerCallback6:: getassemblyreferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백에서 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체를 사용 하 여 ICorProfilerAssemblyReferenceProvider:: addassemblyreference 메서드를 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 구조체](profiling-structures.md)
- [GetAssemblyReferences 메서드](icorprofilercallback6-getassemblyreferences-method.md)
- [AddAssemblyReference 메서드](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
