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
ms.openlocfilehash: f6feed9f59715f9a2801cd3a2a99a087957d4377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715071"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="d4195-102">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4195-102">IAssemblyName Interface</span></span>

<span data-ttu-id="d4195-103">어셈블리의 고유 id를 설명 하 고 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4195-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4195-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-104">Methods</span></span>  
  
|<span data-ttu-id="d4195-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-105">Method</span></span>|<span data-ttu-id="d4195-106">설명</span><span class="sxs-lookup"><span data-stu-id="d4195-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4195-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="d4195-108">이 개체의 단순 복사본을 만듭니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="d4195-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d4195-109">Finalize 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="d4195-110">`IAssemblyName`소멸자가 호출 되기 전에이 개체가 리소스를 해제 하 고 다른 정리 작업을 수행할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4195-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="d4195-111">GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="d4195-112">이 개체가 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="d4195-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d4195-113">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="d4195-114">이 개체가 참조 하는 어셈블리의 단순한 암호화 되지 않은 이름을 가져옵니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="d4195-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d4195-115">GetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="d4195-116">지정 된에서 참조 하는 속성에 대 한 포인터를 가져옵니다 `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="d4195-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="d4195-117">GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="d4195-118">이 개체가 참조 하는 어셈블리에 대 한 버전 정보를 가져옵니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="d4195-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d4195-119">IsEqual 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="d4195-120">지정 된 `IAssemblyName` `IAssemblyName` 비교 플래그에 따라 지정 된 개체가이와 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4195-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="d4195-121">SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="d4195-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="d4195-122">지정 된에서 참조 하는 속성의 값을 설정 합니다 `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="d4195-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d4195-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4195-123">Requirements</span></span>  

 <span data-ttu-id="d4195-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4195-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4195-125">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d4195-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d4195-126">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4195-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4195-127">참조</span><span class="sxs-lookup"><span data-stu-id="d4195-127">See also</span></span>

- [<span data-ttu-id="d4195-128">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4195-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="d4195-129">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d4195-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
