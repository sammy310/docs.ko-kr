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
ms.openlocfilehash: 42f5685a9a976be7a3a73badf286f77216e43106
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741236"
---
# <a name="certfreeauthenticodesignerinfo-function"></a><span data-ttu-id="6f4ae-102">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="6f4ae-102">CertFreeAuthenticodeSignerInfo Function</span></span>
<span data-ttu-id="6f4ae-103">에 할당 된 리소스를 해제 합니다 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4ae-103">Frees resources allocated for the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f4ae-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f4ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f4ae-105">Parameters</span></span>  
 `pSignerInfo`  
 <span data-ttu-id="6f4ae-106">[in, out] 해제할 서명자 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4ae-106">[in, out] Signer information to be released.</span></span> <span data-ttu-id="6f4ae-107">참조 된 [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4ae-107">See the [AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f4ae-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6f4ae-108">Return Value</span></span>  
 <span data-ttu-id="6f4ae-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="6f4ae-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="6f4ae-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f4ae-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4ae-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f4ae-111">See also</span></span>

- [<span data-ttu-id="6f4ae-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="6f4ae-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
