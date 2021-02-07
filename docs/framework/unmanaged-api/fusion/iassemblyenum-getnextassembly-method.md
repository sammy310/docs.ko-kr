---
description: '자세한 정보: IAssemblyEnum:: GetNextAssembly 메서드'
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
ms.openlocfilehash: 52b264b1d8efad54168a6bf69fd0c715cbfa7e2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760820"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="5bd57-103">IAssemblyEnum::GetNextAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="5bd57-103">IAssemblyEnum::GetNextAssembly Method</span></span>

<span data-ttu-id="5bd57-104">이 [Iassemblyenum](iassemblyenum-interface.md) 개체에 포함 된 다음 [IAssemblyName](iassemblyname-interface.md) 에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-104">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd57-105">구문</span><span class="sxs-lookup"><span data-stu-id="5bd57-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bd57-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bd57-106">Parameters</span></span>  

 `pvReserved`  
 <span data-ttu-id="5bd57-107">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5bd57-108">`pvReserved` 는 null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-108">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="5bd57-109">제한이 반환 된 `IAssemblyName` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-109">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5bd57-110">진행 향후 확장성을 위해 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="5bd57-111">`dwFlags` 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd57-111">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd57-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bd57-112">Requirements</span></span>  

 <span data-ttu-id="5bd57-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bd57-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd57-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5bd57-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5bd57-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd57-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd57-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bd57-116">See also</span></span>

- [<span data-ttu-id="5bd57-117">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bd57-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5bd57-118">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bd57-118">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
