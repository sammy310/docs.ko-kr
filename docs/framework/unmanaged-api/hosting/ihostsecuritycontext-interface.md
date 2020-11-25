---
title: IHostSecurityContext 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724808"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="97883-102">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97883-102">IHostSecurityContext Interface</span></span>

<span data-ttu-id="97883-103">CLR (공용 언어 런타임)이 호스트에서 구현 하는 보안 컨텍스트 정보를 유지 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97883-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97883-104">메서드</span><span class="sxs-lookup"><span data-stu-id="97883-104">Methods</span></span>  
  
|<span data-ttu-id="97883-105">메서드</span><span class="sxs-lookup"><span data-stu-id="97883-105">Method</span></span>|<span data-ttu-id="97883-106">설명</span><span class="sxs-lookup"><span data-stu-id="97883-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97883-107">Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="97883-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="97883-108">`IHostSecurityContext` [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)에 대 한 호출에서 반환 된 인스턴스의 복제본을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97883-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97883-109">설명</span><span class="sxs-lookup"><span data-stu-id="97883-109">Remarks</span></span>  

 <span data-ttu-id="97883-110">호스트는 CLR 및 사용자 코드를 모두 사용 하 여 스레드 토큰에 대 한 모든 코드 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97883-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="97883-111">또한 코드 액세스가 제한 된 비동기 작업 또는 코드 포인트로 전체 보안 컨텍스트 정보를 전달 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97883-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="97883-112">`IHostSecurityContext` 런타임에 불투명 한이 보안 컨텍스트 정보를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="97883-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="97883-113">런타임은를 사용 하 여이 정보 `Capture` 를 캡처하여 스레드 풀 작업자 항목 디스패치, 종료자 실행 및 모듈 및 클래스 생성자 간에 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="97883-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97883-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97883-114">Requirements</span></span>  

 <span data-ttu-id="97883-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97883-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97883-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="97883-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97883-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97883-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97883-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97883-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97883-119">참조</span><span class="sxs-lookup"><span data-stu-id="97883-119">See also</span></span>

- [<span data-ttu-id="97883-120">ICLRHostProtectionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97883-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="97883-121">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97883-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="97883-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97883-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
