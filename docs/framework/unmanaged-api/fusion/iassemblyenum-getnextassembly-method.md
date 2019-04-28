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
ms.openlocfilehash: 9a77e468363b59e76e55aa24d97d064189ad297e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697474"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="9096d-102">IAssemblyEnum::GetNextAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="9096d-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="9096d-103">다음에 대 한 포인터를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 이 포함 된 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9096d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9096d-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9096d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9096d-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="9096d-106">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9096d-107">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="9096d-108">[out] 반환 된 `IAssemblyName` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9096d-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="9096d-110">`dwFlags` 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9096d-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9096d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9096d-111">Requirements</span></span>  
 <span data-ttu-id="9096d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9096d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9096d-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9096d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9096d-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9096d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9096d-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9096d-115">See also</span></span>

- [<span data-ttu-id="9096d-116">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9096d-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="9096d-117">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9096d-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
