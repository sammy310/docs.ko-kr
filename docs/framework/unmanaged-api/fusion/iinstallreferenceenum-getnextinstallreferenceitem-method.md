---
title: IInstallReferenceEnum::GetNextInstallReferenceItem 메서드
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202380"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="f4a77-102">IInstallReferenceEnum::GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="f4a77-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="f4a77-103">다음에 대 한 포인터를 가져옵니다 [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) 이 포함 된 개체 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a77-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4a77-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4a77-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4a77-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="f4a77-106">[out] 반환 된 `IInstallReferenceItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f4a77-107">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="f4a77-108">0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f4a77-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="f4a77-110">null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4a77-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a77-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4a77-111">Requirements</span></span>  
 <span data-ttu-id="f4a77-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4a77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a77-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f4a77-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="f4a77-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f4a77-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4a77-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4a77-115">See also</span></span>

- [<span data-ttu-id="f4a77-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4a77-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="f4a77-117">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4a77-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
