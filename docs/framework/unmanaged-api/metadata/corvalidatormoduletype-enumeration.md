---
title: CorValidatorModuleType 열거형
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: a8dc09ee9f0f0fd79060bb86c599ab40a285153b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448764"
---
# <a name="corvalidatormoduletype-enumeration"></a>CorValidatorModuleType 열거형
모듈의 유형을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|모듈의 형식이 잘못 되었습니다.|  
|`ValidatorModuleTypeMin`|`CorValidatorModuleType` 열거형의 최소값입니다.|  
|`ValidatorModuleTypePE`|모듈은 PE (이식 가능한 실행) 파일입니다.|  
|`ValidatorModuleTypeObj`|모듈은 .obj 파일입니다.|  
|`ValidatorModuleTypeEnc`|이 모듈은 편집 하며 계속 하기 디버거 세션입니다.|  
|`ValidatorModuleTypeIncr`|모듈은 증분 방식으로 작성 된 모듈입니다.|  
|`ValidatorModuleTypeMax`|`CorValidatorModuleType` 열거형의 최대값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
