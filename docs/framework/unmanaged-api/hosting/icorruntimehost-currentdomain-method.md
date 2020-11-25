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
ms.openlocfilehash: 33d56354a560949b2f451df9ef82d4f433951195
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715565"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="32a31-102">ICorRuntimeHost::CurrentDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="32a31-102">ICorRuntimeHost::CurrentDomain Method</span></span>

<span data-ttu-id="32a31-103"><xref:System.AppDomain?displayProperty=nameWithType>현재 스레드에 로드 된 도메인을 나타내는 형식의 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32a31-104">구문</span><span class="sxs-lookup"><span data-stu-id="32a31-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32a31-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="32a31-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="32a31-106">제한이 <xref:System.AppDomain?displayProperty=nameWithType> 스레드의 현재 응용 프로그램 도메인을 나타내는 형식의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="32a31-107">이 포인터는 형식화 되어 `IUnknown` 있으므로 호출자가 일반적으로를 호출 `QueryInterface` 하 여 형식의 포인터를 가져와야 합니다 <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="32a31-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32a31-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="32a31-108">Return Value</span></span>  
  
|<span data-ttu-id="32a31-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32a31-109">HRESULT</span></span>|<span data-ttu-id="32a31-110">설명</span><span class="sxs-lookup"><span data-stu-id="32a31-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32a31-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="32a31-111">S_OK</span></span>|<span data-ttu-id="32a31-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-112">The operation was successful.</span></span>|  
|<span data-ttu-id="32a31-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="32a31-113">S_FALSE</span></span>|<span data-ttu-id="32a31-114">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="32a31-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32a31-115">E_FAIL</span></span>|<span data-ttu-id="32a31-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="32a31-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="32a31-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32a31-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32a31-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32a31-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32a31-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32a31-121">Requirements</span></span>  

 <span data-ttu-id="32a31-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32a31-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32a31-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="32a31-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32a31-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32a31-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32a31-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="32a31-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a31-126">참조</span><span class="sxs-lookup"><span data-stu-id="32a31-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="32a31-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="32a31-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
