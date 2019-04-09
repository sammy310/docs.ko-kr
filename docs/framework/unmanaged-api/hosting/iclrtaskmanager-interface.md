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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134661"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="4f228-102">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f228-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="4f228-103">메서드는 CLR (공용 언어 런타임) 호스트 하는 명시적으로 요청을 허용 하는 새 작업 만들기, 현재 실행 중인 작업을 가져오고 설정 언어와 작업에 대 한 문화권을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f228-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-104">Methods</span></span>  
  
|<span data-ttu-id="4f228-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-105">Method</span></span>|<span data-ttu-id="4f228-106">설명</span><span class="sxs-lookup"><span data-stu-id="4f228-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f228-107">CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="4f228-108">CLR에서 만든 새 명시적으로 요청 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4f228-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="4f228-109">GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="4f228-110">가져옵니다는 `ICLRTask` 현재 실행 중인 태스크를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="4f228-111">GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="4f228-112">현재 실행 중인 작업의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="4f228-113">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="4f228-114">호스트에서 현재 실행 중인 작업에 대 한 로캘 식별자가 수정 하는 CLR에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="4f228-115">SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="4f228-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="4f228-116">호스트에서 현재 실행 중인 작업에서 사용자 인터페이스 로캘 식별자를 수정에 공용 언어 런타임을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f228-117">설명</span><span class="sxs-lookup"><span data-stu-id="4f228-117">Remarks</span></span>  
 <span data-ttu-id="4f228-118">호스트 된 환경에서 실행 중인 각 태스크 호스트 쪽에 대 한 두 표현 (인스턴스의 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) 및 clr (인스턴스의 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="4f228-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="4f228-119">호스트 또는 CLR 작업의 만들기를 시작할 수 있지만 호스트 측 표현을 호스트와 작업에 대 한 CLR 간의 성공적인 통신을 위해 해당 CLR 쪽 표현으로 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="4f228-120">두 개체가 생성 되어 인스턴스화하기 전에 운영 체제 스레드에서 관리 코드를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f228-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f228-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f228-121">Requirements</span></span>  
 <span data-ttu-id="4f228-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f228-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f228-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f228-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f228-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4f228-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4f228-125">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4f228-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f228-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="4f228-126">See also</span></span>

- [<span data-ttu-id="4f228-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f228-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4f228-128">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f228-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4f228-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f228-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="4f228-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f228-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
