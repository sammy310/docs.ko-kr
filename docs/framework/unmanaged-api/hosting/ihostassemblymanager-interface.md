---
description: '자세히 알아보기: IHostAssemblyManager 인터페이스'
title: IHostAssemblyManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: 649771f79e65039adfa8c0ade9f167b1679bb917
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708998"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="f8d87-103">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8d87-103">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="f8d87-104">호스트가 CLR (공용 언어 런타임) 또는 호스트에서 로드 해야 하는 어셈블리 집합을 지정 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d87-104">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8d87-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f8d87-105">Methods</span></span>  
  
|<span data-ttu-id="f8d87-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f8d87-106">Method</span></span>|<span data-ttu-id="f8d87-107">설명</span><span class="sxs-lookup"><span data-stu-id="f8d87-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8d87-108">GetAssemblyStore 메서드</span><span class="sxs-lookup"><span data-stu-id="f8d87-108">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="f8d87-109">호스트에서 로드 한 어셈블리 목록을 나타내는 [IHostAssemblyStore](ihostassemblystore-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8d87-109">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="f8d87-110">GetNonHostStoreAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="f8d87-110">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="f8d87-111">호스트에서 CLR을 로드 하는 데 필요한 어셈블리 목록을 나타내는 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8d87-111">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8d87-112">설명</span><span class="sxs-lookup"><span data-stu-id="f8d87-112">Remarks</span></span>  

 <span data-ttu-id="f8d87-113">호스트는 또는를 구현할 필요가 없습니다 `IHostAssemblyManager` `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="f8d87-113">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="f8d87-114">호스트에서를 구현 하는 경우 `IHostAssemblyManager` 도 구현 해야 `IHostAssemblyStore` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d87-114">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="f8d87-115">런타임은 `IHostAssemblyManager` IID_IHostAssemblyManager의를 사용 하 여 초기화할 때 [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) 를 호출 하 여에 대해 쿼리 합니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="f8d87-115">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d87-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8d87-116">Requirements</span></span>  

 <span data-ttu-id="f8d87-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8d87-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d87-118">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f8d87-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8d87-119">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d87-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8d87-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d87-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d87-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8d87-121">See also</span></span>

- [<span data-ttu-id="f8d87-122">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8d87-122">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f8d87-123">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8d87-123">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="f8d87-124">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8d87-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="f8d87-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8d87-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
