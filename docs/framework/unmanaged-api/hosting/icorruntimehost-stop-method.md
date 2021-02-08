---
description: '자세히 알아보기: ICorRuntimeHost:: Stop 메서드'
title: ICorRuntimeHost::Stop 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: b44c77b7d0fe3a078efa11756f5fac7ba400ca5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789595"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="7c645-103">ICorRuntimeHost::Stop 메서드</span><span class="sxs-lookup"><span data-stu-id="7c645-103">ICorRuntimeHost::Stop Method</span></span>

<span data-ttu-id="7c645-104">런타임에 현재 프로세스에 대 한 코드의 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-104">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c645-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c645-105">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7c645-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="7c645-106">Return Value</span></span>  
  
|<span data-ttu-id="7c645-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c645-107">HRESULT</span></span>|<span data-ttu-id="7c645-108">설명</span><span class="sxs-lookup"><span data-stu-id="7c645-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c645-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c645-109">S_OK</span></span>|<span data-ttu-id="7c645-110">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-110">The operation was successful.</span></span>|  
|<span data-ttu-id="7c645-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7c645-111">S_FALSE</span></span>|<span data-ttu-id="7c645-112">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-112">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7c645-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c645-113">E_FAIL</span></span>|<span data-ttu-id="7c645-114">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-114">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7c645-115">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-115">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7c645-116">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-116">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c645-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c645-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c645-118">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c645-119">설명</span><span class="sxs-lookup"><span data-stu-id="7c645-119">Remarks</span></span>  

 <span data-ttu-id="7c645-120">`Stop`프로세스가 종료 될 때 코드의 실행이 중지 되기 때문에 일반적으로 메서드를 호출 하는 것은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-120">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c645-121">를 호출한 후에는 `Stop` 동일한 프로세스로 CLR을 다시 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-121">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c645-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c645-122">Requirements</span></span>  

 <span data-ttu-id="7c645-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c645-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c645-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7c645-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c645-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c645-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c645-126">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7c645-126">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c645-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c645-127">See also</span></span>

- [<span data-ttu-id="7c645-128">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c645-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
