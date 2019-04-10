---
title: ICorPublishProcess 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08dfa3ddbfd9cffdb0cb88d0325e5703a854668a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182964"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="c178e-102">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c178e-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="c178e-103">액세스 하는 프로세스에 대 한 정보를 표시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c178e-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c178e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-104">Methods</span></span>  
  
|<span data-ttu-id="c178e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-105">Method</span></span>|<span data-ttu-id="c178e-106">설명</span><span class="sxs-lookup"><span data-stu-id="c178e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c178e-107">EnumAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="c178e-108">가져옵니다는 [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) 이 참조 하는 프로세스에서 응용 프로그램 도메인을 포함 하는 인스턴스 `ICorPublishProcess`합니다.</span><span class="sxs-lookup"><span data-stu-id="c178e-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c178e-109">GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="c178e-110">이 참조 하는 프로세스에 대 한 실행 파일의 전체 경로 가져옵니다 `ICorPublishProcess`합니다.</span><span class="sxs-lookup"><span data-stu-id="c178e-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c178e-111">GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="c178e-112">이 참조 하는 프로세스에 대 한 운영 체제 식별자를 가져옵니다 `ICorPublishProcess`합니다.</span><span class="sxs-lookup"><span data-stu-id="c178e-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="c178e-113">IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="c178e-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="c178e-114">이 프로세스를 참조 하는지 여부를 나타내는 값을 가져옵니다 `ICorPublishProcess` 실행 관리 코드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c178e-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c178e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c178e-115">Requirements</span></span>  
 <span data-ttu-id="c178e-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c178e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c178e-117">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c178e-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c178e-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c178e-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c178e-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="c178e-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c178e-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="c178e-120">See also</span></span>

- [<span data-ttu-id="c178e-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c178e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c178e-122">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="c178e-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
