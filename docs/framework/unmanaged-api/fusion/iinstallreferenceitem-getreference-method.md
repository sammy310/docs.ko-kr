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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131674"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="4ad78-102">IInstallReferenceItem::GetReference 메서드</span><span class="sxs-lookup"><span data-stu-id="4ad78-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="4ad78-103">이 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체가 나타내는 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 구조체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad78-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ad78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ad78-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ad78-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="4ad78-106">제한이 반환 된 `FUSION_INSTALL_REFERENCE` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4ad78-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4ad78-108">`dwFlags` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4ad78-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="4ad78-110">`pvReserved`은 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad78-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad78-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ad78-111">Requirements</span></span>  
 <span data-ttu-id="4ad78-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad78-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad78-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4ad78-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4ad78-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad78-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad78-115">참조</span><span class="sxs-lookup"><span data-stu-id="4ad78-115">See also</span></span>

- [<span data-ttu-id="4ad78-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ad78-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="4ad78-117">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="4ad78-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
