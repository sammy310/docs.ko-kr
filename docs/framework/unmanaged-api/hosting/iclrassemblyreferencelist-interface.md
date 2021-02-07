---
description: '자세히 알아보기: ICLRAssemblyReferenceList 인터페이스'
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
ms.openlocfilehash: f5ef4efd343ebc18c443482f4697a3d299c5aac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716813"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="22d3b-103">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d3b-103">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="22d3b-104">호스트가 아닌 CLR (공용 언어 런타임)에 의해 로드 되는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="22d3b-104">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22d3b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="22d3b-105">Methods</span></span>  
  
|<span data-ttu-id="22d3b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="22d3b-106">Method</span></span>|<span data-ttu-id="22d3b-107">설명</span><span class="sxs-lookup"><span data-stu-id="22d3b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22d3b-108">IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="22d3b-108">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="22d3b-109">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22d3b-109">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="22d3b-110">IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="22d3b-110">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="22d3b-111">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22d3b-111">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22d3b-112">설명</span><span class="sxs-lookup"><span data-stu-id="22d3b-112">Remarks</span></span>  

 <span data-ttu-id="22d3b-113">[ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) 메서드를 호출 하 여의 인스턴스에 대 한 포인터를 가져옵니다 `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="22d3b-113">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22d3b-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22d3b-114">Requirements</span></span>  

 <span data-ttu-id="22d3b-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22d3b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22d3b-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="22d3b-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22d3b-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d3b-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22d3b-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22d3b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d3b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22d3b-119">See also</span></span>

- [<span data-ttu-id="22d3b-120">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d3b-120">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="22d3b-121">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d3b-121">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="22d3b-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22d3b-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
