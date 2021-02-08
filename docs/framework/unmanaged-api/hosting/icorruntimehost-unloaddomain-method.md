---
description: '자세히 알아보기: ICorRuntimeHost:: UnloadDomain 메서드'
title: ICorRuntimeHost::UnloadDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: b191f2342778b2f2ed7ddb7b1fb548c73be96599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799399"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="0c708-103">ICorRuntimeHost::UnloadDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0c708-103">ICorRuntimeHost::UnloadDomain Method</span></span>

<span data-ttu-id="0c708-104">현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-104">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c708-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c708-105">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c708-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c708-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="0c708-107">진행 <xref:System._AppDomain?displayProperty=nameWithType> 언로드할 도메인을 나타내는 형식의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-107">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c708-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0c708-108">Return Value</span></span>  
  
|<span data-ttu-id="0c708-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c708-109">HRESULT</span></span>|<span data-ttu-id="0c708-110">설명</span><span class="sxs-lookup"><span data-stu-id="0c708-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c708-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c708-111">S_OK</span></span>|<span data-ttu-id="0c708-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-112">The operation was successful.</span></span>|  
|<span data-ttu-id="0c708-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0c708-113">S_FALSE</span></span>|<span data-ttu-id="0c708-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="0c708-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c708-115">E_FAIL</span></span>|<span data-ttu-id="0c708-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0c708-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0c708-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c708-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c708-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c708-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c708-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c708-121">Requirements</span></span>  

 <span data-ttu-id="0c708-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c708-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c708-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0c708-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c708-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c708-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c708-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0c708-125">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c708-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c708-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="0c708-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c708-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
