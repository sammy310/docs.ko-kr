---
title: IAssemblyEnum::GetNextAssembly 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796681"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="214a4-102">IAssemblyEnum::GetNextAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="214a4-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="214a4-103">이 [Iassemblyenum](iassemblyenum-interface.md) 개체에 포함 된 다음 [IAssemblyName](iassemblyname-interface.md) 에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214a4-104">구문</span><span class="sxs-lookup"><span data-stu-id="214a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="214a4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="214a4-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="214a4-106">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="214a4-107">`pvReserved`는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="214a4-108">제한이 반환 `IAssemblyName` 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="214a4-109">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="214a4-110">`dwFlags`0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="214a4-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="214a4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="214a4-111">Requirements</span></span>  
 <span data-ttu-id="214a4-112">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="214a4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="214a4-113">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="214a4-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="214a4-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="214a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214a4-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="214a4-115">See also</span></span>

- [<span data-ttu-id="214a4-116">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="214a4-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="214a4-117">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="214a4-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
