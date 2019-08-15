---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eef89c9e560da65d670ffe59649b44a64f8da6a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039601"
---
# <a name="axl_authenticode_timestamper_info-structure"></a>AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조
Authenticode 타임스탬퍼 정보를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|Description|  
|------------|-----------------|  
|`cbSize`|이 구조체의 크기입니다.|  
|`dwError`|오류 코드입니다.|  
|`algHash`|해시 알고리즘입니다.|  
|`ftTimestamp`|타임스탬프의 시간입니다.|  
|`pChainContext`|타임스탬퍼의 체인 컨텍스트입니다.  [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.|  
  
## <a name="see-also"></a>참고자료

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
