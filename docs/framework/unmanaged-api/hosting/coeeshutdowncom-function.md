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
ms.openlocfilehash: 4e85a9a98bf0550fa906f8b905c73890948f4ac1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124936"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="08cda-102">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="08cda-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="08cda-103">CLR (공용 언어 런타임)에서 RCW (런타임 호출 가능 래퍼) 내에 포함 된 모든 인터페이스 포인터를 해제 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="08cda-104">이는 모든 RCW 캐시를 해제 하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="08cda-105">이 전역 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="08cda-106">대신 특정 런타임에 대 한 진입점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08cda-107">구문</span><span class="sxs-lookup"><span data-stu-id="08cda-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="08cda-108">주의</span><span class="sxs-lookup"><span data-stu-id="08cda-108">Remarks</span></span>  
 <span data-ttu-id="08cda-109">`CoEEShutDownCOM` 함수는 먼저 모든 컨텍스트와 모든 캐시에서 모든 Rcw를 해제 한 다음 설치 프로그램에서 기존에 존재 하는 모든 중단 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="08cda-110">DLL 언로드가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="08cda-111">이 함수는 프로세스에 로드 되는 모든 런타임에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="08cda-112">.NET Framework 4부터 영향을 원하는 특정 런타임에이 함수에 대 한 진입점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="08cda-113">진입점을 가져오려면 [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드를 호출 하 고 "CoEEShutDownCOM"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08cda-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08cda-114">Requirements</span></span>  
 <span data-ttu-id="08cda-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08cda-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08cda-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="08cda-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08cda-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08cda-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08cda-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08cda-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cda-119">참조</span><span class="sxs-lookup"><span data-stu-id="08cda-119">See also</span></span>

- [<span data-ttu-id="08cda-120">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="08cda-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
