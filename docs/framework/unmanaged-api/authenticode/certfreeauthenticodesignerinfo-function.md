---
title: CertFreeAuthenticodeSignerInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
ms.openlocfilehash: a233e0b8d17b9ee61b1991086f794c9fb20f89e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099827"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="826c4-102">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="826c4-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="826c4-103">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체에 할당 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="826c4-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="826c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="826c4-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="826c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="826c4-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="826c4-106">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="826c4-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="826c4-107">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="826c4-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="826c4-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="826c4-108">Return Value</span></span>  
 <span data-ttu-id="826c4-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="826c4-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="826c4-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="826c4-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="826c4-111">참조</span><span class="sxs-lookup"><span data-stu-id="826c4-111">See also</span></span>

- [<span data-ttu-id="826c4-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="826c4-112">Authenticode</span></span>](index.md)
