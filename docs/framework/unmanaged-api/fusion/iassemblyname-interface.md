---
title: IAssemblyName 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134324"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="35b47-102">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35b47-102">IAssemblyName Interface</span></span>
<span data-ttu-id="35b47-103">어셈블리의 고유 id를 설명 하 고 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35b47-104">메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-104">Methods</span></span>  
  
|<span data-ttu-id="35b47-105">메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-105">Method</span></span>|<span data-ttu-id="35b47-106">설명</span><span class="sxs-lookup"><span data-stu-id="35b47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35b47-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="35b47-108">이 `IAssemblyName` 개체의 단순 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="35b47-109">Finalize 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="35b47-110">소멸자가 호출 되기 전에이 `IAssemblyName` 개체가 리소스를 해제 하 고 다른 정리 작업을 수행할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="35b47-111">GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="35b47-112">이 `IAssemblyName` 개체에서 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="35b47-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="35b47-114">이 `IAssemblyName` 개체에서 참조 하는 어셈블리의 단순한 암호화 되지 않은 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="35b47-115">GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="35b47-116">지정 된 `PropertyId`에서 참조 하는 속성에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="35b47-117">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="35b47-118">이 `IAssemblyName` 개체에서 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="35b47-119">IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="35b47-120">지정 된 비교 플래그를 기준으로 지정 된 `IAssemblyName` 개체가이 `IAssemblyName`와 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="35b47-121">SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="35b47-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="35b47-122">지정 된 `PropertyId`에서 참조 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35b47-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35b47-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35b47-123">Requirements</span></span>  
 <span data-ttu-id="35b47-124">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35b47-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b47-125">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="35b47-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="35b47-126">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b47-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b47-127">참조</span><span class="sxs-lookup"><span data-stu-id="35b47-127">See also</span></span>

- [<span data-ttu-id="35b47-128">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35b47-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="35b47-129">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35b47-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
