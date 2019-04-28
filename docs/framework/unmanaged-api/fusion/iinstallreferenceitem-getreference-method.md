---
title: IInstallReferenceItem::GetReference 메서드
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757679"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="4a6a8-102">IInstallReferenceItem::GetReference 메서드</span><span class="sxs-lookup"><span data-stu-id="4a6a8-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="4a6a8-103">포인터를 가져 합니다 [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) 이 표시 되는 구조 [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a6a8-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a6a8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a6a8-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="4a6a8-106">[out] 반환 된 `FUSION_INSTALL_REFERENCE` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4a6a8-107">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4a6a8-108">`dwFlags` 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4a6a8-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4a6a8-110">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6a8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a6a8-111">Requirements</span></span>  
 <span data-ttu-id="4a6a8-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a6a8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6a8-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4a6a8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4a6a8-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6a8-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a6a8-115">See also</span></span>

- [<span data-ttu-id="4a6a8-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a6a8-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="4a6a8-117">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="4a6a8-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
