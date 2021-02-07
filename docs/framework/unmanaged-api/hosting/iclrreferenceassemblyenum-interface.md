---
description: '자세히 알아보기: ICLRReferenceAssemblyEnum 인터페이스'
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
ms.openlocfilehash: a7e522623c254940a6dbb8d22bf7f2fec76a1072
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689003"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="02438-103">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02438-103">ICLRReferenceAssemblyEnum Interface</span></span>

<span data-ttu-id="02438-104">호스트에서 해당 id를 만들거나 이해할 필요 없이 CLR (공용 언어 런타임)의 내부 어셈블리 id 데이터를 사용 하 여 파일이 나 스트림이 참조 하는 어셈블리 집합을 조작할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="02438-104">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02438-105">메서드</span><span class="sxs-lookup"><span data-stu-id="02438-105">Methods</span></span>  
  
|<span data-ttu-id="02438-106">메서드</span><span class="sxs-lookup"><span data-stu-id="02438-106">Method</span></span>|<span data-ttu-id="02438-107">설명</span><span class="sxs-lookup"><span data-stu-id="02438-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02438-108">Get 메서드</span><span class="sxs-lookup"><span data-stu-id="02438-108">Get Method</span></span>](iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="02438-109">제공 된 인덱스에서 어셈블리 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02438-109">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02438-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02438-110">Requirements</span></span>  

 <span data-ttu-id="02438-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02438-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02438-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02438-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02438-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02438-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02438-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02438-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02438-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02438-115">See also</span></span>

- [<span data-ttu-id="02438-116">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02438-116">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="02438-117">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02438-117">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="02438-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02438-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
