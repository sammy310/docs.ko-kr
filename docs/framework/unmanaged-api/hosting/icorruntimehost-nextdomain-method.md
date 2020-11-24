---
title: ICorRuntimeHost::NextDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 598c46d50d7b4a67c1b2c0d844c9b12deb12a428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671371"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="a964f-102">ICorRuntimeHost::NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="a964f-102">ICorRuntimeHost::NextDomain Method</span></span>

<span data-ttu-id="a964f-103">열거형의 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a964f-104">구문</span><span class="sxs-lookup"><span data-stu-id="a964f-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a964f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a964f-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="a964f-106">진행 [Enumdomains](icorruntimehost-enumdomains-method.md)호출을 통해 가져온 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-106">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a964f-107">제한이 <xref:System._AppDomain?displayProperty=nameWithType> 열거형의 다음 도메인을 나타내는 형식에 대 한 인터페이스 포인터 이거나, 더 이상 도메인이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a964f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a964f-108">Return Value</span></span>  
  
|<span data-ttu-id="a964f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a964f-109">HRESULT</span></span>|<span data-ttu-id="a964f-110">설명</span><span class="sxs-lookup"><span data-stu-id="a964f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a964f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a964f-111">S_OK</span></span>|<span data-ttu-id="a964f-112">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-112">The operation was successful.</span></span>|  
|<span data-ttu-id="a964f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a964f-113">S_FALSE</span></span>|<span data-ttu-id="a964f-114">작업을 완료 하지 못했거나 열거에 도메인이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="a964f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a964f-115">E_FAIL</span></span>|<span data-ttu-id="a964f-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a964f-117">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a964f-118">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a964f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a964f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a964f-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a964f-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a964f-121">Requirements</span></span>  

 <span data-ttu-id="a964f-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a964f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a964f-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a964f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a964f-124">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a964f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a964f-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a964f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a964f-126">참조</span><span class="sxs-lookup"><span data-stu-id="a964f-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="a964f-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a964f-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
