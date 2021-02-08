---
description: '자세히 알아보기: IHostIoCompletionManager:: Bind 메서드'
title: IHostIoCompletionManager::Bind 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 2105bf06c23f70588d0c1bc0cd849b8e810d121e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784862"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="8ad9e-103">IHostIoCompletionManager::Bind 메서드</span><span class="sxs-lookup"><span data-stu-id="8ad9e-103">IHostIoCompletionManager::Bind Method</span></span>

<span data-ttu-id="8ad9e-104">[Createio완성도 포트](ihostiocompletionmanager-createiocompletionport-method.md)에 대 한 이전 호출에 의해 만들어진 i/o 완료 포트에 지정 된 핸들을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-104">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ad9e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8ad9e-105">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ad9e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ad9e-106">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="8ad9e-107">진행 바인딩할 i/o 완료 포트 `hHandle` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-107">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="8ad9e-108">의 값 `hPort` 이 null 인 경우 `hHandle` 는 기본 i/o 완료 포트에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-108">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="8ad9e-109">진행 바인딩할 운영 체제 핸들 `hPort` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-109">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ad9e-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="8ad9e-110">Return Value</span></span>  
  
|<span data-ttu-id="8ad9e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ad9e-111">HRESULT</span></span>|<span data-ttu-id="8ad9e-112">설명</span><span class="sxs-lookup"><span data-stu-id="8ad9e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ad9e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ad9e-113">S_OK</span></span>|<span data-ttu-id="8ad9e-114">`Bind` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-114">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="8ad9e-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ad9e-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ad9e-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ad9e-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ad9e-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ad9e-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-118">The call timed out.</span></span>|  
|<span data-ttu-id="8ad9e-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ad9e-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ad9e-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ad9e-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ad9e-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ad9e-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ad9e-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ad9e-123">E_FAIL</span></span>|<span data-ttu-id="8ad9e-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ad9e-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ad9e-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ad9e-127">설명</span><span class="sxs-lookup"><span data-stu-id="8ad9e-127">Remarks</span></span>  

 <span data-ttu-id="8ad9e-128">I/o 완료 포트는를 호출 하 여 만듭니다 `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="8ad9e-128">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="8ad9e-129">CLR은를 호출 하 여 `Bind` 핸들을 해당 포트에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-129">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ad9e-130">I/o 요청이 완료 되 면 호스트는 [IclrioOnComplete manager::](iclriocompletionmanager-oncomplete-method.md) 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-130">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ad9e-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ad9e-131">Requirements</span></span>  

 <span data-ttu-id="8ad9e-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ad9e-133">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8ad9e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ad9e-134">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ad9e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ad9e-135">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ad9e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad9e-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ad9e-136">See also</span></span>

- [<span data-ttu-id="8ad9e-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ad9e-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
