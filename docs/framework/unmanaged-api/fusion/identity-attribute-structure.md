---
description: '다음에 대 한 자세한 정보: IDENTITY_ATTRIBUTE 구조체'
title: IDENTITY_ATTRIBUTE 구조체
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
ms.openlocfilehash: 52610961ab202fc79351073eac1846a1a63889e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800177"
---
# <a name="identity_attribute-structure"></a>IDENTITY_ATTRIBUTE 구조체

[Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스에 대 한 메타 데이터 특성 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`pszNamespace`|특성이 있는 네임 스페이스를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.|  
|`pszName`|특성의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.|  
|`pszValue`|특성의 값을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>설명  

 구조체에는 `IDENTITY_ATTRIBUTE` null로 끝나는 문자열에 대 한 세 개의 포인터가 포함 됩니다. 이 세 문자열은 하나의 특성을 설명 합니다.  
  
 구조체의 인스턴스는 `IDENTITY_ATTRIBUTE` [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) 구조체의 인스턴스와 연결 됩니다. 구조체에는 `IDENTITY_ATTRIBUTE` 실제 문자열이 포함 되 고, 해당 `IDENTITY_ATTRIBUTE_BLOB` 구조에는 구조에 나열 된 세 개의 문자열로의 오프셋이 나열 `IDENTITY_ATTRIBUTE` 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IDefinitionIdentity 인터페이스](idefinitionidentity-interface.md)
- [IDENTITY_ATTRIBUTE_BLOB 구조체](identity-attribute-blob-structure.md)
- [Fusion 구조체](fusion-structures.md)
