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
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099766"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="ae9da-102">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="ae9da-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="ae9da-103">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조체에 할당 된 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9da-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9da-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae9da-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae9da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae9da-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="ae9da-106">[in, out] 해제할 타임스탬퍼 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9da-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="ae9da-107">[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ae9da-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae9da-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae9da-108">Return Value</span></span>  
 <span data-ttu-id="ae9da-109">함수가 정상적으로 실행되는 경우 `S_OK`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9da-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="ae9da-110">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae9da-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9da-111">참조</span><span class="sxs-lookup"><span data-stu-id="ae9da-111">See also</span></span>

- [<span data-ttu-id="ae9da-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="ae9da-112">Authenticode</span></span>](index.md)
