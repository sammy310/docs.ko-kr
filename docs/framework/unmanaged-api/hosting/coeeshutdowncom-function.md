---
title: CoEEShutDownCOM 함수
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ddef35b1b707cc5c962402e880923dca7d4d9d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208152"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="85e32-102">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="85e32-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="85e32-103">CLR (공용 언어 런타임) 런타임 호출 가능 래퍼 (RCW) 내에서 보유 하는 모든 인터페이스 포인터가 해제 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="85e32-104">이 효과가 모든 RCW 캐시를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="85e32-105">이 전역 함수에서 사용 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="85e32-106">대신, 특정 런타임에 대 한 진입점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e32-107">구문</span><span class="sxs-lookup"><span data-stu-id="85e32-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="85e32-108">설명</span><span class="sxs-lookup"><span data-stu-id="85e32-108">Remarks</span></span>  
 <span data-ttu-id="85e32-109">`CoEEShutDownCOM` 함수는 먼저 모든 컨텍스트 및 모든 캐시에 있는 모든 Rcw를 해제 하 고 다음 설치 프로그램에서 기존의 모든 중지 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="85e32-110">DLL 언로드 없습니다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="85e32-111">이 함수는 모든 런타임을 프로세스로 로드 되는 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="85e32-112">부터는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], 영향을 주려는 특정 런타임에서이 함수에 대 한 진입점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="85e32-113">진입점을 가져오려면 호출 합니다 [iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드 "CoEEShutDownCOM"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85e32-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e32-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85e32-114">Requirements</span></span>  
 <span data-ttu-id="85e32-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85e32-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e32-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85e32-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85e32-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="85e32-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85e32-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e32-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e32-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="85e32-119">See also</span></span>

- [<span data-ttu-id="85e32-120">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="85e32-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
