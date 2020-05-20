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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615880"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="f0d11-102">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0d11-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="f0d11-103">호스트가 아닌 CLR (공용 언어 런타임)에 의해 로드 되는 어셈블리 목록을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d11-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0d11-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f0d11-104">Methods</span></span>  
  
|<span data-ttu-id="f0d11-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f0d11-105">Method</span></span>|<span data-ttu-id="f0d11-106">설명</span><span class="sxs-lookup"><span data-stu-id="f0d11-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0d11-107">IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="f0d11-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="f0d11-108">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0d11-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="f0d11-109">IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="f0d11-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="f0d11-110">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0d11-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0d11-111">설명</span><span class="sxs-lookup"><span data-stu-id="f0d11-111">Remarks</span></span>  
 <span data-ttu-id="f0d11-112">[ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) 메서드를 호출 하 여의 인스턴스에 대 한 포인터를 가져옵니다 `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="f0d11-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d11-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0d11-113">Requirements</span></span>  
 <span data-ttu-id="f0d11-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d11-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d11-115">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0d11-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0d11-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d11-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0d11-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d11-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d11-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0d11-118">See also</span></span>

- [<span data-ttu-id="f0d11-119">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0d11-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f0d11-120">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0d11-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="f0d11-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0d11-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
