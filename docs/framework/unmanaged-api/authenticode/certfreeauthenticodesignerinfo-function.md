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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 357a2ca0ffc733adb14a21624cbe28fb754c8240
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776735"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="fd471-102">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="fd471-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="fd471-103">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체에 할당 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd471-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd471-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd471-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd471-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd471-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="fd471-106">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="fd471-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="fd471-107">[AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd471-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd471-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="fd471-108">Return Value</span></span>  
 <span data-ttu-id="fd471-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="fd471-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="fd471-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd471-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd471-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd471-111">See also</span></span>

- [<span data-ttu-id="fd471-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="fd471-112">Authenticode</span></span>](index.md)
