---
description: '자세한 정보: IInstallReferenceEnum:: GetNextInstallReferenceItem 메서드'
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
ms.openlocfilehash: d410407fe16a46b45786ff74f694aaa8931be542
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800122"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="7ff98-103">IInstallReferenceEnum::GetNextInstallReferenceItem 메서드</span><span class="sxs-lookup"><span data-stu-id="7ff98-103">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="7ff98-104">이 [Iinstallreferenceitem](iinstallreferenceenum-interface.md) 개체에 포함 된 다음 [Iinstallreferenceitem](iinstallreferenceitem-interface.md) 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-104">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ff98-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ff98-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ff98-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ff98-106">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="7ff98-107">제한이 반환 된 `IInstallReferenceItem` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-107">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7ff98-108">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7ff98-109">`dwFlags` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-109">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7ff98-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7ff98-111">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff98-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ff98-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ff98-112">Requirements</span></span>  

 <span data-ttu-id="7ff98-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff98-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff98-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7ff98-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7ff98-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff98-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff98-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ff98-116">See also</span></span>

- [<span data-ttu-id="7ff98-117">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ff98-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="7ff98-118">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ff98-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
