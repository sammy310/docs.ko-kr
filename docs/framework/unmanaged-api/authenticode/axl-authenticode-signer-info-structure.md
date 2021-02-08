---
description: '다음에 대 한 자세한 정보: AXL_AUTHENTICODE_SIGNER_INFO 구조체'
title: AXL_AUTHENTICODE_SIGNER_INFO 구조
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 940652cf184e26f141df806b060c391333d1bb95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781963"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="a866e-103">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="a866e-103">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="a866e-104">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-104">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a866e-105">구문</span><span class="sxs-lookup"><span data-stu-id="a866e-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a866e-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a866e-106">Members</span></span>  
  
|<span data-ttu-id="a866e-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a866e-107">Member</span></span>|<span data-ttu-id="a866e-108">설명</span><span class="sxs-lookup"><span data-stu-id="a866e-108">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="a866e-109">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-109">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="a866e-110">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-110">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="a866e-111">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-111">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="a866e-112">해시입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-112">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="a866e-113">설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-113">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="a866e-114">설명의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-114">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="a866e-115">서명자의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a866e-115">The chain context of the signer.</span></span> <span data-ttu-id="a866e-116">[CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a866e-116">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a866e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a866e-117">See also</span></span>

- [<span data-ttu-id="a866e-118">Authenticode</span><span class="sxs-lookup"><span data-stu-id="a866e-118">Authenticode</span></span>](index.md)
