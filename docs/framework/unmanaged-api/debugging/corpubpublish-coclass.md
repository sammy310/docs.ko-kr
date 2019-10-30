---
title: CorpubPublish Coclass
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: 89af99fab1f1265701e0dbfe74a46000cb3bfaa6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132147"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="9b984-102">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="9b984-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="9b984-103">애플리케이션 도메인 및 프로세스에 대한 정보를 게시하기 위한 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b984-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b984-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="9b984-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-105">Interfaces</span></span>  
  
|<span data-ttu-id="9b984-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-106">Interface</span></span>|<span data-ttu-id="9b984-107">설명</span><span class="sxs-lookup"><span data-stu-id="9b984-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="9b984-108">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="9b984-109">프로세스 및 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="9b984-110">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="9b984-111">프로세스의 응용 프로그램 도메인에 대 한 정보를 나타내고 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="9b984-112">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="9b984-113">프로세스 내에 현재 존재 하는 응용 프로그램 도메인의 컬렉션을 트래버스하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="9b984-114">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="9b984-115">컴퓨터에서 실행 중인 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="9b984-116">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b984-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="9b984-117">컴퓨터에서 실행 중인 프로세스의 컬렉션을 트래버스하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b984-118">주의</span><span class="sxs-lookup"><span data-stu-id="9b984-118">Remarks</span></span>  
 <span data-ttu-id="9b984-119">일반적인 게시 시나리오에는 응용 프로그램 도메인 내 컴퓨터에서 실행 되는 관리 코드를 디버깅 하려는 개발자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="9b984-120">호스팅 환경이 프로세스 내에서 둘 이상의 응용 프로그램 도메인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="9b984-121">개발자는 그래픽 사용자 인터페이스를 사용 하거나 다른 방법을 사용 하 여 컴퓨터에서 실행 중인 모든 프로세스를 나열 하 고 특정 프로세스를 선택 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="9b984-122">이 목록에는 관리 코드를 실행 하는 프로세스 내의 모든 응용 프로그램 도메인이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="9b984-123">그러면 개발자는 특정 응용 프로그램 도메인을 식별 하 고 해당 도메인에 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b984-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b984-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b984-124">Requirements</span></span>  
 <span data-ttu-id="9b984-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9b984-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b984-126">**헤더:** CorPub. idl</span><span class="sxs-lookup"><span data-stu-id="9b984-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="9b984-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b984-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b984-128">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b984-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b984-129">참조</span><span class="sxs-lookup"><span data-stu-id="9b984-129">See also</span></span>

- [<span data-ttu-id="9b984-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="9b984-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
