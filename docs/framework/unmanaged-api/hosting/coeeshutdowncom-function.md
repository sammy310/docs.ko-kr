---
description: '자세히 알아보기: CoEEShutDownCOM 함수'
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
ms.openlocfilehash: 4f1ac8107c9a121ebf52ef21a5f2c9006880914f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799865"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="f1768-103">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="f1768-103">CoEEShutDownCOM Function</span></span>

<span data-ttu-id="f1768-104">CLR (공용 언어 런타임)에서 RCW (런타임 호출 가능 래퍼) 내에 포함 된 모든 인터페이스 포인터를 해제 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-104">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="f1768-105">이는 모든 RCW 캐시를 해제 하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-105">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="f1768-106">이 전역 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-106">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="f1768-107">대신 특정 런타임에 대 한 진입점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-107">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1768-108">구문</span><span class="sxs-lookup"><span data-stu-id="f1768-108">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f1768-109">설명</span><span class="sxs-lookup"><span data-stu-id="f1768-109">Remarks</span></span>  

 <span data-ttu-id="f1768-110">함수는 먼저 모든 컨텍스트와 모든 캐시에서 모든 `CoEEShutDownCOM` rcw를 해제 한 다음 설치 프로그램에서 기존에 존재 하는 모든 중단 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-110">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="f1768-111">DLL 언로드가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-111">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="f1768-112">이 함수는 프로세스에 로드 되는 모든 런타임에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-112">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="f1768-113">.NET Framework 4부터 영향을 원하는 특정 런타임에이 함수에 대 한 진입점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-113">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="f1768-114">진입점을 가져오려면 [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) 메서드를 호출 하 고 "CoEEShutDownCOM"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-114">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1768-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1768-115">Requirements</span></span>  

 <span data-ttu-id="f1768-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1768-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1768-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f1768-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1768-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1768-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1768-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1768-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1768-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1768-120">See also</span></span>

- [<span data-ttu-id="f1768-121">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f1768-121">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
