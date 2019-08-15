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
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="60afd-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="60afd-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="60afd-103">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60afd-104">구문</span><span class="sxs-lookup"><span data-stu-id="60afd-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="60afd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="60afd-105">Members</span></span>  
  
|<span data-ttu-id="60afd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="60afd-106">Member</span></span>|<span data-ttu-id="60afd-107">Description</span><span class="sxs-lookup"><span data-stu-id="60afd-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="60afd-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="60afd-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="60afd-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="60afd-111">타임스탬프의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="60afd-112">타임스탬퍼의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="60afd-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="60afd-113">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60afd-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60afd-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="60afd-114">See also</span></span>

- [<span data-ttu-id="60afd-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="60afd-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
