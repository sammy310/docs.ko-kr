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
ms.openlocfilehash: a311166e79f930e763b0338451f6356c8c93f929
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670144"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="8b6ca-102">ICLRDebugManager::SetSymbolReadingPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="8b6ca-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>

<span data-ttu-id="8b6ca-103">PDB (프로그램 데이터베이스) 파일을 읽기 위한 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="8b6ca-104">이 정책은 줄 번호와 파일에 대 한 정보가 호출 스택에 포함 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b6ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="8b6ca-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b6ca-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b6ca-106">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="8b6ca-107">진행 [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) 열거의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b6ca-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="8b6ca-108">Return Value</span></span>  
  
|<span data-ttu-id="8b6ca-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b6ca-109">HRESULT</span></span>|<span data-ttu-id="8b6ca-110">설명</span><span class="sxs-lookup"><span data-stu-id="8b6ca-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b6ca-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b6ca-111">S_OK</span></span>|<span data-ttu-id="8b6ca-112">`SetSymbolReadingPolicy` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="8b6ca-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b6ca-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b6ca-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b6ca-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b6ca-115">E_FAIL</span></span>|<span data-ttu-id="8b6ca-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b6ca-117">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b6ca-118">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b6ca-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b6ca-119">Requirements</span></span>  

 <span data-ttu-id="8b6ca-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b6ca-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8b6ca-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b6ca-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b6ca-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b6ca-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b6ca-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b6ca-124">참조</span><span class="sxs-lookup"><span data-stu-id="8b6ca-124">See also</span></span>

- [<span data-ttu-id="8b6ca-125">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b6ca-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
