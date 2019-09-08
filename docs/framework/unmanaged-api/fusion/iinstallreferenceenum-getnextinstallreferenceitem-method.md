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
ms.openlocfilehash: 20e2bff4257df64f761fd8fff880643d4e786748
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796451"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="41147-102">IInstallReferenceEnum::GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="41147-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="41147-103">이 [Iinstallreferenceitem](iinstallreferenceenum-interface.md) 개체에 포함 된 다음 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41147-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41147-104">구문</span><span class="sxs-lookup"><span data-stu-id="41147-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41147-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41147-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="41147-106">제한이 반환 `IInstallReferenceItem` 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="41147-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="41147-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41147-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="41147-108">`dwFlags`0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41147-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="41147-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41147-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="41147-110">`pvReserved`는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41147-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41147-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41147-111">Requirements</span></span>  
 <span data-ttu-id="41147-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41147-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41147-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="41147-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41147-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41147-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41147-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="41147-115">See also</span></span>

- [<span data-ttu-id="41147-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41147-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="41147-117">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41147-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
