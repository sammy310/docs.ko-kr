---
title: ICLRDebugManager::SetSymbolReadingPolicy 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2dc3d350f5c97736b3b65c814a668195aceef2b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132823"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="4e0dc-102">ICLRDebugManager::SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="4e0dc-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="4e0dc-103">프로그램 데이터베이스 (PDB) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="4e0dc-104">정책은 호출 스택의 줄 번호 및 파일에 대 한 정보 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e0dc-105">구문</span><span class="sxs-lookup"><span data-stu-id="4e0dc-105">Syntax</span></span>  
  
```  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e0dc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e0dc-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="4e0dc-107">[in] 멤버는 [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-107">[in] A member of the [ESymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e0dc-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4e0dc-108">Return Value</span></span>  
  
|<span data-ttu-id="4e0dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e0dc-109">HRESULT</span></span>|<span data-ttu-id="4e0dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e0dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e0dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e0dc-111">S_OK</span></span>|<span data-ttu-id="4e0dc-112">`SetSymbolReadingPolicy` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="4e0dc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e0dc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e0dc-114">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e0dc-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e0dc-115">E_FAIL</span></span>|<span data-ttu-id="4e0dc-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e0dc-117">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e0dc-118">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e0dc-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e0dc-119">Requirements</span></span>  
 <span data-ttu-id="4e0dc-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e0dc-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e0dc-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e0dc-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e0dc-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4e0dc-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e0dc-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e0dc-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0dc-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e0dc-124">See also</span></span>

- [<span data-ttu-id="4e0dc-125">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e0dc-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
