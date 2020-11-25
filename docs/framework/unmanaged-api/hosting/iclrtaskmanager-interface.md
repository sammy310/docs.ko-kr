---
title: ICLRTaskManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: 1170b29c01275b108a6ccdf6e324c96d97c10c82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732452"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="b7926-102">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7926-102">ICLRTaskManager Interface</span></span>

<span data-ttu-id="b7926-103">호스트에서 CLR (공용 언어 런타임)이 새 작업을 만들고, 현재 실행 중인 작업을 가져오고, 작업의 지리적 언어와 문화권을 설정할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7926-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-104">Methods</span></span>  
  
|<span data-ttu-id="b7926-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-105">Method</span></span>|<span data-ttu-id="b7926-106">설명</span><span class="sxs-lookup"><span data-stu-id="b7926-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7926-107">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-107">CreateTask Method</span></span>](iclrtaskmanager-createtask-method.md)|<span data-ttu-id="b7926-108">CLR이 새 [ICLRTask](iclrtask-interface.md) 인스턴스를 만들도록 명시적으로 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-108">Requests explicitly that the CLR create a new [ICLRTask](iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="b7926-109">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-109">GetCurrentTask Method</span></span>](iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="b7926-110">`ICLRTask`현재 실행 중인 작업을 나타내는 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="b7926-111">GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-111">GetCurrentTaskType Method</span></span>](iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="b7926-112">현재 실행 중인 작업의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="b7926-113">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-113">SetLocale Method</span></span>](iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="b7926-114">호스트에서 현재 실행 중인 작업의 로캘 식별자를 수정 했음을 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="b7926-115">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="b7926-115">SetUILocale Method</span></span>](iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="b7926-116">호스트에서 현재 실행 중인 작업의 사용자 인터페이스 로캘 식별자를 수정 했음을 공용 언어 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7926-117">설명</span><span class="sxs-lookup"><span data-stu-id="b7926-117">Remarks</span></span>  

 <span data-ttu-id="b7926-118">호스팅된 환경에서 실행 되는 각 작업에는 호스트 측 ( [IHostTask](ihosttask-interface.md)의 인스턴스) 및 CLR 쪽 ( [ICLRTask](iclrtask-interface.md)의 인스턴스) 모두에 대 한 표현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](iclrtask-interface.md)).</span></span> <span data-ttu-id="b7926-119">호스트 또는 CLR에서 작업 만들기를 시작할 수 있지만 호스트와 작업에 대 한 CLR 간의 성공적인 통신을 보장 하기 위해 호스트 쪽 표현이 해당 CLR 쪽 표현과 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="b7926-120">운영 체제 스레드에서 관리 코드를 실행 하려면 먼저 두 개체를 만들고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7926-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7926-121">Requirements</span></span>  

 <span data-ttu-id="b7926-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7926-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7926-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7926-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7926-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7926-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7926-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7926-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7926-126">참조</span><span class="sxs-lookup"><span data-stu-id="b7926-126">See also</span></span>

- [<span data-ttu-id="b7926-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7926-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b7926-128">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7926-128">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b7926-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7926-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="b7926-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7926-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
