---
title: ICLRProbingAssemblyEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094296"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="e9f67-102">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9f67-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="e9f67-103">만들거나 해당 id를 이해 하지 않고도 내부 공용 언어 런타임 (CLR)에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져오려면 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9f67-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9f67-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e9f67-104">Methods</span></span>  
  
|<span data-ttu-id="e9f67-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e9f67-105">Method</span></span>|<span data-ttu-id="e9f67-106">설명</span><span class="sxs-lookup"><span data-stu-id="e9f67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9f67-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="e9f67-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="e9f67-108">지정된 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9f67-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9f67-109">설명</span><span class="sxs-lookup"><span data-stu-id="e9f67-109">Remarks</span></span>  
 <span data-ttu-id="e9f67-110">와 같은 메서드와 [iclrassemblyidentitymanager:: Getprobingassembliesfromreference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) 반환을 `ICLRProbingAssemblyEnum` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e9f67-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f67-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9f67-111">Requirements</span></span>  
 <span data-ttu-id="e9f67-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e9f67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f67-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9f67-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9f67-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e9f67-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9f67-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f67-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9f67-116">See also</span></span>

- [<span data-ttu-id="e9f67-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9f67-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e9f67-118">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9f67-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e9f67-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9f67-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
