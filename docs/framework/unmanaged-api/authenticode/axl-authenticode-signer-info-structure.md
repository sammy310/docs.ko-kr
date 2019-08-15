---
title: AXL_AUTHENTICODE_SIGNER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038436"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="44327-102">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="44327-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="44327-103">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44327-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44327-104">구문</span><span class="sxs-lookup"><span data-stu-id="44327-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="44327-105">멤버</span><span class="sxs-lookup"><span data-stu-id="44327-105">Members</span></span>  
  
|<span data-ttu-id="44327-106">멤버</span><span class="sxs-lookup"><span data-stu-id="44327-106">Member</span></span>|<span data-ttu-id="44327-107">Description</span><span class="sxs-lookup"><span data-stu-id="44327-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="44327-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="44327-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="44327-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="44327-111">해시입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="44327-112">설명입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="44327-113">설명의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="44327-114">서명자의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="44327-114">The chain context of the signer.</span></span> <span data-ttu-id="44327-115">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44327-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44327-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="44327-116">See also</span></span>

- [<span data-ttu-id="44327-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="44327-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
