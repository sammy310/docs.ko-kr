---
title: CorPEKind 열거형
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 74670a1477546066145bd4bbf2f123a252e10b55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436478"
---
# <a name="corpekind-enumeration"></a>CorPEKind 열거형
[IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)호출에서 반환 된 PE (이식 가능한 실행) 파일을 설명 하는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`peNot`|PE 파일이 아님을 나타냅니다.|  
|`peILOnly`|이 PE 파일에 관리 되는 코드만 포함 되어 있음을 나타냅니다.|  
|`pe32BitRequired`|이 PE 파일에서 Win32 호출을 수행 함을 나타냅니다.|  
|`pe32Plus`|이 PE 파일이 64 비트 플랫폼에서 실행 됨을 나타냅니다.|  
|`pe32Unmanaged`|이 PE 파일이 네이티브 코드 임을 나타냅니다.|  
|pe32BitPreferred|이 PE 파일이 플랫폼 중립적 이며 32 비트 환경에서 로드 되는 것을 선호 함을 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 이러한 값은 비트 조합에서 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
