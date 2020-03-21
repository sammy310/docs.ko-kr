---
title: CorSymSearchPolicyAttributes 열거형
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178343"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes 열거형
기호 판독기를 검색할 때 사용할 정책을 지정합니다. 이러한 상수는 [ISymUnmanaged바인더2:GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) 및 [ISymUnmanaged바인더3:GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) 메서드에서 사용됩니다.  
  
> [!IMPORTANT]
> 신뢰할 수 없는 원본에서 프로그램 데이터베이스(PDB) 파일을 여는 것은 보안 위험입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`AllowRegistryAccess`|기호 검색 경로에 대 한 레지스트리를 쿼리합니다.|  
|`AllowSymbolServerAccess`|기호 서버에 액세스합니다.|  
|`AllowOriginalPathAccess`|디버그 디렉토리에 지정된 경로를 검색합니다.|  
|`AllowReferencePathAccess`|.exe 파일이 있는 위치에 있는 PDB를 검색합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 코르심.idl, 코르심.h  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 열거형](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
