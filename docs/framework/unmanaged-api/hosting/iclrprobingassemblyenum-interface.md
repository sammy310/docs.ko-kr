---
description: '자세히 알아보기: ICLRProbingAssemblyEnum 인터페이스'
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
ms.openlocfilehash: 1fd11e237f02bab85ec2b41df49d7d8a2f27e1e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716512"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="83c7c-103">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c7c-103">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="83c7c-104">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR (공용 언어 런타임)의 내부에 있는 어셈블리의 id 정보를 사용 하 여 어셈블리의 검색 id를 가져올 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c7c-104">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83c7c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="83c7c-105">Methods</span></span>  
  
|<span data-ttu-id="83c7c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="83c7c-106">Method</span></span>|<span data-ttu-id="83c7c-107">설명</span><span class="sxs-lookup"><span data-stu-id="83c7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83c7c-108">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="83c7c-108">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="83c7c-109">지정 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83c7c-109">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83c7c-110">설명</span><span class="sxs-lookup"><span data-stu-id="83c7c-110">Remarks</span></span>  

 <span data-ttu-id="83c7c-111">[ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) 와 같은 메서드는 인스턴스를 반환 `ICLRProbingAssemblyEnum` 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c7c-111">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c7c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83c7c-112">Requirements</span></span>  

 <span data-ttu-id="83c7c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83c7c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c7c-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="83c7c-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83c7c-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c7c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83c7c-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c7c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c7c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83c7c-117">See also</span></span>

- [<span data-ttu-id="83c7c-118">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c7c-118">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="83c7c-119">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c7c-119">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="83c7c-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c7c-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
