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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117751"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="99d67-102">IAssemblyEnum::GetNextAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="99d67-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="99d67-103">다음에 대 한 포인터를 가져옵니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 이 포함 된 [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d67-104">구문</span><span class="sxs-lookup"><span data-stu-id="99d67-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d67-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99d67-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="99d67-106">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-106">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="99d67-107">null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-107">must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="99d67-108">[out] 반환 된 `IAssemblyName` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="99d67-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-109">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="99d67-110">0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99d67-110">must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d67-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99d67-111">Requirements</span></span>  
 <span data-ttu-id="99d67-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="99d67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d67-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="99d67-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="99d67-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="99d67-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="99d67-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="99d67-115">See also</span></span>

- [<span data-ttu-id="99d67-116">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99d67-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="99d67-117">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99d67-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
