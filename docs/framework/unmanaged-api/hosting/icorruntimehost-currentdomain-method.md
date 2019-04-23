---
title: ICorRuntimeHost::CurrentDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb5ff5300a7fd2577e602b3077dd816cf7dfbe2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181389"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="d3001-102">ICorRuntimeHost::CurrentDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="d3001-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="d3001-103">형식의 인터페이스 포인터를 가져옵니다 <xref:System.AppDomain?displayProperty=nameWithType> 현재 스레드에서 로드 된 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3001-104">구문</span><span class="sxs-lookup"><span data-stu-id="d3001-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3001-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3001-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d3001-106">[out] 형식의 포인터 <xref:System.AppDomain?displayProperty=nameWithType> 스레드의 현재 응용 프로그램 도메인을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="d3001-107">이 포인터를 입력 `IUnknown`호출자에 게 일반적으로 호출 해야 하므로 `QueryInterface` 형식의 포인터를 가져오려면 <xref:System._AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3001-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d3001-108">Return Value</span></span>  
  
|<span data-ttu-id="d3001-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3001-109">HRESULT</span></span>|<span data-ttu-id="d3001-110">설명</span><span class="sxs-lookup"><span data-stu-id="d3001-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3001-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3001-111">S_OK</span></span>|<span data-ttu-id="d3001-112">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-112">The operation was successful.</span></span>|  
|<span data-ttu-id="d3001-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d3001-113">S_FALSE</span></span>|<span data-ttu-id="d3001-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d3001-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3001-115">E_FAIL</span></span>|<span data-ttu-id="d3001-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d3001-117">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d3001-118">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3001-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3001-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3001-120">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3001-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3001-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3001-121">Requirements</span></span>  
 <span data-ttu-id="d3001-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3001-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3001-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d3001-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3001-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d3001-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3001-125">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d3001-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3001-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="d3001-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="d3001-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3001-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
