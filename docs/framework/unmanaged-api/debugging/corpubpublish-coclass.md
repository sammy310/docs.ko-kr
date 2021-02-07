---
description: '자세한 정보: CorpubPublish Coclass'
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
ms.openlocfilehash: fdf4be6ff2d20391e989998cd0045ed27d602561
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661691"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="7d806-103">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="7d806-103">CorpubPublish Coclass</span></span>

<span data-ttu-id="7d806-104">애플리케이션 도메인 및 프로세스에 대한 정보를 게시하기 위한 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-104">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d806-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d806-105">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="7d806-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-106">Interfaces</span></span>  
  
|<span data-ttu-id="7d806-107">인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-107">Interface</span></span>|<span data-ttu-id="7d806-108">설명</span><span class="sxs-lookup"><span data-stu-id="7d806-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="7d806-109">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-109">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="7d806-110">프로세스 및 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-110">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="7d806-111">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-111">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="7d806-112">프로세스의 응용 프로그램 도메인에 대 한 정보를 나타내고 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-112">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="7d806-113">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-113">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="7d806-114">프로세스 내에 현재 존재 하는 응용 프로그램 도메인의 컬렉션을 트래버스하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-114">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="7d806-115">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-115">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="7d806-116">컴퓨터에서 실행 중인 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-116">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="7d806-117">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d806-117">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="7d806-118">컴퓨터에서 실행 중인 프로세스의 컬렉션을 트래버스하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-118">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d806-119">설명</span><span class="sxs-lookup"><span data-stu-id="7d806-119">Remarks</span></span>  

 <span data-ttu-id="7d806-120">일반적인 게시 시나리오에는 응용 프로그램 도메인 내 컴퓨터에서 실행 되는 관리 코드를 디버깅 하려는 개발자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-120">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="7d806-121">호스팅 환경이 프로세스 내에서 둘 이상의 응용 프로그램 도메인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-121">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="7d806-122">개발자는 그래픽 사용자 인터페이스를 사용 하거나 다른 방법을 사용 하 여 컴퓨터에서 실행 중인 모든 프로세스를 나열 하 고 특정 프로세스를 선택 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-122">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="7d806-123">이 목록에는 관리 코드를 실행 하는 프로세스 내의 모든 응용 프로그램 도메인이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-123">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="7d806-124">그러면 개발자는 특정 응용 프로그램 도메인을 식별 하 고 해당 도메인에 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d806-124">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d806-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d806-125">Requirements</span></span>  

 <span data-ttu-id="7d806-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d806-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d806-127">**헤더:** CorPub. idl</span><span class="sxs-lookup"><span data-stu-id="7d806-127">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="7d806-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d806-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d806-129">**.NET Framework 버전:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d806-129">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d806-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d806-130">See also</span></span>

- [<span data-ttu-id="7d806-131">디버깅</span><span class="sxs-lookup"><span data-stu-id="7d806-131">Debugging</span></span>](index.md)
