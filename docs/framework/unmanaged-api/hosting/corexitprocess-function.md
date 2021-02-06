---
description: '다음에 대 한 자세한 정보: CorExitProcess 함수'
title: CorExitProcess 함수
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 68d33dec76387e103a34e99c529a4e7aff7535b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649587"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="49322-103">CorExitProcess 함수</span><span class="sxs-lookup"><span data-stu-id="49322-103">CorExitProcess Function</span></span>

<span data-ttu-id="49322-104">현재 관리 되지 않는 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="49322-104">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="49322-105">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49322-105">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="49322-106">대신 [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49322-106">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49322-107">구문</span><span class="sxs-lookup"><span data-stu-id="49322-107">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49322-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49322-108">Parameters</span></span>  

 `exitCode`  
 <span data-ttu-id="49322-109">프로세스 종료 코드를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="49322-109">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49322-110">설명</span><span class="sxs-lookup"><span data-stu-id="49322-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49322-111">.NET Framework 4부터는 `CorExitProcess` 기존 api가 바인딩된 런타임 뿐만 아니라 프로세스에서 시작 된 모든 런타임을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="49322-111">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49322-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49322-112">Requirements</span></span>  

 <span data-ttu-id="49322-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="49322-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49322-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="49322-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49322-115">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49322-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49322-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49322-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49322-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49322-117">See also</span></span>

- [<span data-ttu-id="49322-118">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="49322-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
