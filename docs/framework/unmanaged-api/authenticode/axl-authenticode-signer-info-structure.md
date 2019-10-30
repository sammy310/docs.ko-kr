---
title: AXL_AUTHENTICODE_SIGNER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 00132bb378d69c0db9fe9d762407707346238917
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132508"
---
# <a name="axl_authenticode_signer_info-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO 구조
Authenticode 서명자 정보를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
|`pChainContext`|서명자의 체인 컨텍스트입니다. [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.|  
  
## <a name="see-also"></a>참조

- [Authenticode](index.md)
