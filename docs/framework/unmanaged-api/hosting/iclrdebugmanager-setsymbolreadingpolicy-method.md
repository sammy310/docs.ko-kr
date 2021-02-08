---
description: '자세히 알아보기: ICLRDebugManager:: SetSymbolReadingPolicy 메서드'
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
ms.openlocfilehash: 2c0862f3c572808ffbf418b275e1ad1c62c2ac89
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781950"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="5d74b-103">ICLRDebugManager::SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="5d74b-103">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>

<span data-ttu-id="5d74b-104">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-104">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="5d74b-105">이 정책은 줄 번호와 파일에 대 한 정보가 호출 스택에 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-105">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d74b-106">구문</span><span class="sxs-lookup"><span data-stu-id="5d74b-106">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d74b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d74b-107">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="5d74b-108">진행 [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) 열거의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-108">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d74b-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5d74b-109">Return Value</span></span>  
  
|<span data-ttu-id="5d74b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d74b-110">HRESULT</span></span>|<span data-ttu-id="5d74b-111">설명</span><span class="sxs-lookup"><span data-stu-id="5d74b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d74b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d74b-112">S_OK</span></span>|<span data-ttu-id="5d74b-113">`SetSymbolReadingPolicy` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-113">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="5d74b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d74b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d74b-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d74b-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d74b-116">E_FAIL</span></span>|<span data-ttu-id="5d74b-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-117">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d74b-118">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-118">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d74b-119">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-119">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d74b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d74b-120">Requirements</span></span>  

 <span data-ttu-id="5d74b-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d74b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d74b-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5d74b-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d74b-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d74b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d74b-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d74b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d74b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d74b-125">See also</span></span>

- [<span data-ttu-id="5d74b-126">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d74b-126">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
