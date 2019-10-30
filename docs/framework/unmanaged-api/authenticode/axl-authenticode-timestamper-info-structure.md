---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: 036397928703aea6199a59ae9c1e66153c30ec7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132500"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="01653-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="01653-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="01653-103">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01653-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01653-104">구문</span><span class="sxs-lookup"><span data-stu-id="01653-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="01653-105">멤버</span><span class="sxs-lookup"><span data-stu-id="01653-105">Members</span></span>  
  
|<span data-ttu-id="01653-106">멤버</span><span class="sxs-lookup"><span data-stu-id="01653-106">Member</span></span>|<span data-ttu-id="01653-107">설명</span><span class="sxs-lookup"><span data-stu-id="01653-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="01653-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="01653-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="01653-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="01653-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="01653-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="01653-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="01653-111">타임스탬프의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="01653-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="01653-112">타임스탬퍼의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="01653-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="01653-113">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="01653-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01653-114">참조</span><span class="sxs-lookup"><span data-stu-id="01653-114">See also</span></span>

- [<span data-ttu-id="01653-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="01653-115">Authenticode</span></span>](index.md)
