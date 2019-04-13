---
title: AXL_AUTHENTICODE_SIGNER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 024837870aade6b0beb76fe758a571b15fd14d59
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107668"
---
# <a name="axlauthenticodesignerinfo-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO 구조
Authenticode 서명자 정보를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbSize`|이 구조체의 크기입니다.|  
|`dwError`|오류 코드입니다.|  
|`algHash`|해시 알고리즘입니다.|  
|`pwszHash`|해시입니다.|  
|`pwszDescription`|설명입니다.|  
|`pwszDescriptionUrl`|설명의 URL입니다.|  
|`pChainContext`|서명자의 체인 컨텍스트입니다. 참조 된 [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) 구조입니다.|  
  
## <a name="see-also"></a>참고자료

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
