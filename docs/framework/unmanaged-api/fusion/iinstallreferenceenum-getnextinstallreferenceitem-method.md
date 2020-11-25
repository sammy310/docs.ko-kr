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
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721103"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="3522e-102">IInstallReferenceEnum::GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="3522e-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="3522e-103">이 [Iinstallreferenceitem](iinstallreferenceenum-interface.md) 개체에 포함 된 다음 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3522e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3522e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3522e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3522e-105">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="3522e-106">제한이 반환 된 `IInstallReferenceItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3522e-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3522e-108">`dwFlags` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3522e-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3522e-110">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3522e-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3522e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3522e-111">Requirements</span></span>  

 <span data-ttu-id="3522e-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3522e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3522e-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3522e-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3522e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3522e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3522e-115">참조</span><span class="sxs-lookup"><span data-stu-id="3522e-115">See also</span></span>

- [<span data-ttu-id="3522e-116">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3522e-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="3522e-117">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3522e-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
