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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703379"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="ebbb2-102">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebbb2-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="ebbb2-103">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR (공용 언어 런타임)의 내부에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져올 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbb2-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ebbb2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ebbb2-104">Methods</span></span>  
  
|<span data-ttu-id="ebbb2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ebbb2-105">Method</span></span>|<span data-ttu-id="ebbb2-106">설명</span><span class="sxs-lookup"><span data-stu-id="ebbb2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ebbb2-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="ebbb2-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="ebbb2-108">지정 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ebbb2-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebbb2-109">설명</span><span class="sxs-lookup"><span data-stu-id="ebbb2-109">Remarks</span></span>  
 <span data-ttu-id="ebbb2-110">[ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) 와 같은 메서드는 인스턴스를 반환 `ICLRProbingAssemblyEnum` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbb2-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebbb2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebbb2-111">Requirements</span></span>  
 <span data-ttu-id="ebbb2-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ebbb2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebbb2-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ebbb2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebbb2-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbb2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebbb2-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebbb2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebbb2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebbb2-116">See also</span></span>

- [<span data-ttu-id="ebbb2-117">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebbb2-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ebbb2-118">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebbb2-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ebbb2-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebbb2-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
