---
description: '자세히 알아보기: Customfcitem 구조체'
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
ms.openlocfilehash: 9bd7b2bb59675bc01e24dc6e6d0ce524f3d35466
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716902"
---
# <a name="customdumpitem-structure"></a>CustomDumpItem 구조체

오류 보고에서 사용자 지정 덤프에 추가할 항목을 설명 합니다.  
  
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
  
|멤버|설명|  
|------------|-----------------|  
|`itemKind`|추가할 항목의 종류를 나타내는 [ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md) 값입니다.|  
|`pReserved`|현재 사용되지 않습니다. 공용 구조체에 추가 된 항목은 포인터 크기 보다 크지 않아야 합니다. `struct`가 필요한 경우 별도로 할당 하 고이를 가리켜야 합니다.|  
  
## <a name="remarks"></a>설명  

 [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) 는 형식의 매개 변수를 사용 `CustomDumpItem` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 구조체](hosting-structures.md)
