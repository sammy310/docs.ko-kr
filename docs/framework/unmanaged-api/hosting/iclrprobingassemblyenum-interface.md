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
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728929"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="899b3-102">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899b3-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="899b3-103">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR (공용 언어 런타임)의 내부에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져올 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="899b3-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="899b3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="899b3-104">Methods</span></span>  
  
|<span data-ttu-id="899b3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="899b3-105">Method</span></span>|<span data-ttu-id="899b3-106">설명</span><span class="sxs-lookup"><span data-stu-id="899b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="899b3-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="899b3-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="899b3-108">지정 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="899b3-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="899b3-109">설명</span><span class="sxs-lookup"><span data-stu-id="899b3-109">Remarks</span></span>  

 <span data-ttu-id="899b3-110">[ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) 와 같은 메서드는 인스턴스를 반환 `ICLRProbingAssemblyEnum` 합니다.</span><span class="sxs-lookup"><span data-stu-id="899b3-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="899b3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="899b3-111">Requirements</span></span>  

 <span data-ttu-id="899b3-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="899b3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="899b3-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="899b3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="899b3-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="899b3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="899b3-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="899b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899b3-116">참조</span><span class="sxs-lookup"><span data-stu-id="899b3-116">See also</span></span>

- [<span data-ttu-id="899b3-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899b3-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="899b3-118">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899b3-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="899b3-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899b3-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
