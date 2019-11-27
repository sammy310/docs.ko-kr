---
title: CVStruct Structure
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: 19ee3097dfe80ba9dcbdaf316db0fd165b50abc6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436418"
---
# <a name="cvstruct-structure"></a>CVStruct Structure
모듈 또는 합성 이미지를 설치할 때 사용되는 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|중요한 변경|주 버전 빌드 번호입니다.|  
|사소한 변경|부 버전 빌드 번호입니다.|  
|하위|하위 빌드 번호입니다.|  
|빌드|빌드 번호입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 구조체](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
