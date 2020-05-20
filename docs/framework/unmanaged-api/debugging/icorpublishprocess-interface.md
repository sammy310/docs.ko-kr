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
ms.openlocfilehash: 8d958e949612b502ab218f5c6b75779174d34e19
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421087"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="69161-102">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69161-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="69161-103">프로세스에 대해 표시할 정보에 액세스 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="69161-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69161-104">메서드</span><span class="sxs-lookup"><span data-stu-id="69161-104">Methods</span></span>  
  
|<span data-ttu-id="69161-105">메서드</span><span class="sxs-lookup"><span data-stu-id="69161-105">Method</span></span>|<span data-ttu-id="69161-106">설명</span><span class="sxs-lookup"><span data-stu-id="69161-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69161-107">EnumAppDomains 메서드</span><span class="sxs-lookup"><span data-stu-id="69161-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="69161-108">이에서 참조 하는 프로세스의 응용 프로그램 도메인을 포함 하는 [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) 인스턴스를 가져옵니다 `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="69161-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="69161-109">GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="69161-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="69161-110">이에서 참조 하는 프로세스에 대 한 실행 파일의 전체 경로를 가져옵니다 `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="69161-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="69161-111">GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="69161-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="69161-112">이에서 참조 하는 프로세스에 대 한 운영 체제 식별자를 가져옵니다 `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="69161-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="69161-113">IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="69161-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="69161-114">이에서 참조 하는 프로세스를 `ICorPublishProcess` 관리 코드를 실행 하는 것으로 알려진 지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="69161-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69161-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69161-115">Requirements</span></span>  
 <span data-ttu-id="69161-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69161-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69161-117">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="69161-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="69161-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69161-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69161-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69161-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69161-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69161-120">See also</span></span>

- [<span data-ttu-id="69161-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69161-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="69161-122">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="69161-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
