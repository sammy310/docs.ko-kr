---
description: '자세히 알아보기: ICorRuntimeHost:: Start 메서드'
title: ICorRuntimeHost::Start 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: d07c0144c7192bc2f57927c294ea472cd6b47f9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789608"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="ccad9-103">ICorRuntimeHost::Start 메서드</span><span class="sxs-lookup"><span data-stu-id="ccad9-103">ICorRuntimeHost::Start Method</span></span>

<span data-ttu-id="ccad9-104">CLR (공용 언어 런타임)을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-104">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccad9-105">구문</span><span class="sxs-lookup"><span data-stu-id="ccad9-105">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ccad9-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="ccad9-106">Return Value</span></span>  
  
|<span data-ttu-id="ccad9-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccad9-107">HRESULT</span></span>|<span data-ttu-id="ccad9-108">설명</span><span class="sxs-lookup"><span data-stu-id="ccad9-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccad9-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccad9-109">S_OK</span></span>|<span data-ttu-id="ccad9-110">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-110">The operation was successful.</span></span>|  
|<span data-ttu-id="ccad9-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ccad9-111">S_FALSE</span></span>|<span data-ttu-id="ccad9-112">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-112">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ccad9-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccad9-113">E_FAIL</span></span>|<span data-ttu-id="ccad9-114">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-114">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ccad9-115">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-115">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="ccad9-116">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-116">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ccad9-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccad9-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccad9-118">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccad9-119">설명</span><span class="sxs-lookup"><span data-stu-id="ccad9-119">Remarks</span></span>  

 <span data-ttu-id="ccad9-120">`Start`CLR은 관리 코드를 실행 하는 첫 번째 요청 시 자동으로 시작 되기 때문에 일반적으로 메서드를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-120">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccad9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccad9-121">Requirements</span></span>  

 <span data-ttu-id="ccad9-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccad9-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccad9-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ccad9-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccad9-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccad9-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccad9-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ccad9-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccad9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccad9-126">See also</span></span>

- [<span data-ttu-id="ccad9-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccad9-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
