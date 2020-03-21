---
title: CustomDumpItem 구조체
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176476"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem 구조체
오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`itemKind`|추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) 값입니다.|  
|`pReserved`|현재 사용되지 않습니다. 공용 구조에 추가된 항목은 포인터 크기보다 커야 합니다. a가 `struct` 필요한 경우 별도로 할당하고 가리가야 합니다.|  
  
## <a name="remarks"></a>설명  
 [ICLR오류 보고 관리자::시작 사용자 지정](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) `CustomDumpItem`덤프 형식의 매개 변수를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorEE.idl  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
