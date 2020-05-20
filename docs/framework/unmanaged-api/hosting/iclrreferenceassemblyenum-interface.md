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
ms.openlocfilehash: 9797c419251127ef07a8c2bee22132c3c2b82e36
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703322"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="85338-102">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85338-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="85338-103">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR (공용 언어 런타임)의 내부 어셈블리 id 데이터를 사용 하 여 파일이 나 스트림이 참조 하는 어셈블리 집합을 조작할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85338-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85338-104">메서드</span><span class="sxs-lookup"><span data-stu-id="85338-104">Methods</span></span>  
  
|<span data-ttu-id="85338-105">메서드</span><span class="sxs-lookup"><span data-stu-id="85338-105">Method</span></span>|<span data-ttu-id="85338-106">설명</span><span class="sxs-lookup"><span data-stu-id="85338-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85338-107">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="85338-107">Get Method</span></span>](iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="85338-108">제공 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85338-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85338-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85338-109">Requirements</span></span>  
 <span data-ttu-id="85338-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85338-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85338-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="85338-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85338-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85338-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85338-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85338-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85338-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85338-114">See also</span></span>

- [<span data-ttu-id="85338-115">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85338-115">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="85338-116">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85338-116">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="85338-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85338-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
