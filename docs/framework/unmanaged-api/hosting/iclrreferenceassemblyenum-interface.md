---
title: ICLRReferenceAssemblyEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32f27d6c15a99282eee20d2563a4ca741238d846
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187405"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="43e5d-102">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e5d-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="43e5d-103">파일 또는 스트림을 만들거나 해당 id를 이해 하지 않고도 내부 공용 언어 런타임 (CLR)에 있는 어셈블리 id 데이터를 사용 하 여 참조 되는 어셈블리의 집합을 조작 하는 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43e5d-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43e5d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="43e5d-104">Methods</span></span>  
  
|<span data-ttu-id="43e5d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="43e5d-105">Method</span></span>|<span data-ttu-id="43e5d-106">설명</span><span class="sxs-lookup"><span data-stu-id="43e5d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43e5d-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="43e5d-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="43e5d-108">제공 된 인덱스에 있는 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="43e5d-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43e5d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43e5d-109">Requirements</span></span>  
 <span data-ttu-id="43e5d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43e5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e5d-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43e5d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43e5d-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="43e5d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43e5d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e5d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e5d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="43e5d-114">See also</span></span>

- [<span data-ttu-id="43e5d-115">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e5d-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="43e5d-116">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e5d-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="43e5d-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43e5d-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
