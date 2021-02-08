---
description: '자세한 정보: IInstallReferenceItem:: GetReference 메서드'
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
ms.openlocfilehash: 88f5ca21b6f3494031e1cd232f71253e39d9e648
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800119"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="99f53-103">IInstallReferenceItem::GetReference 메서드</span><span class="sxs-lookup"><span data-stu-id="99f53-103">IInstallReferenceItem::GetReference Method</span></span>

<span data-ttu-id="99f53-104">이 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체가 나타내는 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 구조체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-104">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f53-105">구문</span><span class="sxs-lookup"><span data-stu-id="99f53-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f53-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99f53-106">Parameters</span></span>  

 `ppRefData`  
 <span data-ttu-id="99f53-107">제한이 반환 된 `FUSION_INSTALL_REFERENCE` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-107">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="99f53-108">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="99f53-109">`dwFlags` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-109">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="99f53-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="99f53-111">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f53-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f53-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99f53-112">Requirements</span></span>  

 <span data-ttu-id="99f53-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99f53-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f53-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="99f53-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="99f53-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f53-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99f53-116">See also</span></span>

- [<span data-ttu-id="99f53-117">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99f53-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="99f53-118">FUSION_INSTALL_REFERENCE 구조체</span><span class="sxs-lookup"><span data-stu-id="99f53-118">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
