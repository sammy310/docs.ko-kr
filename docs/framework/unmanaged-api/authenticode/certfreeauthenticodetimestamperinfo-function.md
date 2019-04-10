---
title: CertFreeAuthenticodeTimestamperInfo 함수
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 355e6c7b1cd77936d5ccfa5ccff7312c8e35ac63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220404"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="3208c-102">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="3208c-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="3208c-103">에 할당 된 리소스를 해제 합니다 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3208c-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3208c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3208c-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3208c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3208c-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="3208c-106">[in, out] 해제할 타임스탬퍼 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3208c-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="3208c-107">참조 된 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3208c-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3208c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3208c-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="3208c-109">함수가 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3208c-109">if the function succeeds.</span></span> <span data-ttu-id="3208c-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3208c-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3208c-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="3208c-111">See also</span></span>

- [<span data-ttu-id="3208c-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3208c-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
