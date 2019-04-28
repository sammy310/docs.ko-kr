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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941650"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="9d9f1-102">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9d9f1-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="9d9f1-103">에 할당 된 리소스를 해제 합니다 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9d9f1-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d9f1-104">Syntax</span></span>  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d9f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d9f1-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="9d9f1-106">[in, out] 해제할 타임스탬퍼 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9d9f1-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="9d9f1-107">참조 된 [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9d9f1-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d9f1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9d9f1-108">Return Value</span></span>  
 <span data-ttu-id="9d9f1-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="9d9f1-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="9d9f1-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d9f1-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9f1-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="9d9f1-111">See also</span></span>

- [<span data-ttu-id="9d9f1-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9d9f1-112">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
