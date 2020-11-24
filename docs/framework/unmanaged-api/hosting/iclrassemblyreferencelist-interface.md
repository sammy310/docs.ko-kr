---
title: ICLRAssemblyReferenceList 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679240"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="a363d-102">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a363d-102">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="a363d-103">호스트가 아닌 CLR (공용 언어 런타임)에 의해 로드 되는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a363d-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a363d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a363d-104">Methods</span></span>  
  
|<span data-ttu-id="a363d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a363d-105">Method</span></span>|<span data-ttu-id="a363d-106">설명</span><span class="sxs-lookup"><span data-stu-id="a363d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a363d-107">IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="a363d-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="a363d-108">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a363d-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="a363d-109">IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="a363d-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="a363d-110">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a363d-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a363d-111">설명</span><span class="sxs-lookup"><span data-stu-id="a363d-111">Remarks</span></span>  

 <span data-ttu-id="a363d-112">[ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) 메서드를 호출 하 여의 인스턴스에 대 한 포인터를 가져옵니다 `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="a363d-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a363d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a363d-113">Requirements</span></span>  

 <span data-ttu-id="a363d-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a363d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a363d-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a363d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a363d-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a363d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a363d-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a363d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a363d-118">참조</span><span class="sxs-lookup"><span data-stu-id="a363d-118">See also</span></span>

- [<span data-ttu-id="a363d-119">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a363d-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a363d-120">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a363d-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="a363d-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a363d-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
